# GSP335
# Secure Workloads in Google Kubernetes Engine: Challenge Lab:
----------------------------------------------------------------------------------------------------
### Set your region and zone
```yaml
gcloud config set compute/region us-central1
gcloud config set compute/zone us-central1-c
```
### Define variables
```yaml
DM_DEPLOYMENT=$(gcloud deployment-manager deployments list | grep NAME | cut -d ' ' -f2)
Cluster_name=$(gcloud deployment-manager deployments describe $DM_DEPLOYMENT | grep security-demo | cut -d ' ' -f2)
Cloud_SQL_Instance=$(gcloud deployment-manager deployments describe $DM_DEPLOYMENT | grep wordpress-db | cut -d ' ' -f2)
Service_Account=$(gcloud deployment-manager deployments describe $DM_DEPLOYMENT | grep sa-wordpress | cut -d ' ' -f2)
```
### Check variables
```yaml
echo $DM_DEPLOYMENT
echo $Cluster_name
echo $Cloud_SQL_Instance
echo $Service_Account
```

### Task 1: Download the necessary files

```yaml
gsutil cp gs://spls/gsp335/gsp335.zip .
unzip gsp335.zip
```

### Task 2: Set up a cluster
- Name: $Cluster_name
- Zone: us-central1-c
- Machine-type: e2-medium
- Nodes: 3
- Enable network policy

```yaml
gcloud container clusters create $Cluster_name \
   --zone us-central1-c \
   --machine-type e2-medium \
   --num-nodes 3 \
   --enable-network-policy
```

```yaml
gcloud container clusters get-credentials $Cluster_name --zone us-central1-c
```

### Task 3: Set up WordPress

###### Set up the Cloud SQL database, database username and password
- Create a Cloud SQL instance called $Cloud_SQL_Instance in us-central1, using the default values.
```yaml
gcloud sql instances create $Cloud_SQL_Instance --region=us-central1
```
- Create a Cloud SQL database for WordPress.
```yaml
gcloud sql databases create wordpress --instance $Cloud_SQL_Instance
```
- Create a user using the following values:
   - Username: wordpress
   - Access from host %
   - Access to the Cloud SQL instance you created
   - Set a password (remember it, you will need later)
```yaml
gcloud sql users create wordpress --instance=$Cloud_SQL_Instance --host=% --password='P@ssword!'
```

###### Create a service account for access to your WordPress database from your WordPress instances
1. Create a service account called Service Account .
```yaml
gcloud iam service-accounts create $Service_Account --display-name $Service_Account
```
2. Bind the service account to your project, give the role roles/cloudsql.client.
```yaml
gcloud projects add-iam-policy-binding $DEVSHELL_PROJECT_ID \
   --member="serviceAccount:$Service_Account@$DEVSHELL_PROJECT_ID.iam.gserviceaccount.com" \
   --role="roles/cloudsql.client"
```
3. Save the service account credentials in a json file.
```yaml
gcloud iam service-accounts keys create key.json --iam-account=$Service_Account@$DEVSHELL_PROJECT_ID.iam.gserviceaccount.com
```
4. Save the service account json file as a secret in your Kubernetes cluster.
```yaml
kubectl create secret generic cloudsql-instance-credentials --from-file key.json
```

5. Save the WordPress database username and password you used in step #4 as secrets in your Kubernetes cluster.

```yaml
kubectl create secret generic cloudsql-db-credentials \
  --from-literal username=wordpress \
  --from-literal password='P@ssword!'
```

###### Create the WordPress deployment and service
1. Use kubectl create -f volume.yaml to create a persistent volume for your WordPress application.
```yaml
kubectl create -f volume.yaml
```
2. Open wordpress.yaml and replace INSTANCE_CONNECTION_NAME with the instance name of your Cloud SQL database (the format is project:region:databasename).
```yaml
sed -i s/INSTANCE_CONNECTION_NAME/$DEVSHELL_PROJECT_ID:us-central1:wordpress/g wordpress.yaml
```
3. Use kubectl apply -f wordpress.yaml to create the WordPress environment.
```yaml
kubectl apply -f wordpress.yaml
```

### Task 4: Setup ingress with TLS
- Set up ingress-nginx environment
   1. Using Helm, install the latest NGINX Ingress controller (ingress-nginx) in the default namespace. Call it ingress-nginx.
```yaml
helm upgrade --install ingress-nginx ingress-nginx \
  --repo https://kubernetes.github.io/ingress-nginx
```

- Set up your DNS record
   1. Check the service ingress-nginx-controller as an external IP address before continuing (kubectl get svc) to the next step.
```yaml
kubectl get svc
```
   2. Run the command:
```yaml
. add_ip.sh
```
You should see record added. You now have a DNS record added of the format YOUR_LAB_USERNAME.labdns.xyz which points to your ingress cluster (the script will output your DNS name).

- Set up cert-manager.io
   1. Install cert-manager.io (make sure you use the right version - v1.10.0 works well with this lab).
```yaml
kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v1.10.0/cert-manager.yaml
```
   2. Edit issuer.yaml and set the email address to Service Account @ Project ID .iam.gserviceaccount.com.
```yaml
sed -i s/LAB_EMAIL_ADDRESS/$Service_Account@$DEVSHELL_PROJECT_ID.iam.gserviceaccount.com/g issuer.yaml
```
   3. Use kubectl apply -f issuer.yaml to setup the letsencrypt prod issuer.
```yaml
kubectl apply -f issuer.yaml
```

- Configure ingress-nginx to use an encrypted certificate for your site
   1. Edit ingress.yaml and set the dns and domain name to your YOUR_LAB_USERNAME.labdns.xyz. Don't forget to remove any _ characters from your username when using it as the dns.
```yaml
HOST_NAME=$(echo $USER | tr -d '_').labdns.xyz
sed -i s/HOST_NAME/${HOST_NAME}/g ingress.yaml
```
   2. Use kubectl apply -f ingress.yaml.
```yaml
kubectl apply -f ingress.yaml
```

### Task 5: Set up a Network Policy

```yaml
echo "apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
name: allow-nginx-access-to-internet
spec:
podSelector:
matchLabels:
    app: nginx-ingress
policyTypes:
- Ingress
ingress:
- {}" >> network-policy.yaml
```

```yaml
kubectl apply -f network-policy.yaml
```

### Task 6: Set up Binary Authorization

```yaml
gcloud services enable \
  container.googleapis.com \
  containeranalysis.googleapis.com \
  binaryauthorization.googleapis.com
```

```yaml
gcloud container clusters update $Cluster_name --enable-binauthz --zone us-central1-c
```

```yaml
gcloud container binauthz policy export > bin-auth-policy.yaml
```

```yaml
nano bin-auth-policy.yaml
```

###### Edit and add the four values and change as:

```yaml
- namePattern: docker.io/library/wordpress:latest
- namePattern: us.gcr.io/k8s-artifacts-prod/ingress-nginx/*
- namePattern: gcr.io/cloudsql-docker/*
- namePattern: quay.io/jetstack/*
defaultAdmissionRule:
 enforcementMode: ENFORCED_BLOCK_AND_AUDIT_LOG
 evaluationMode: ALWAYS_DENY
globalPolicyEvaluationMode: ENABLE
```

```yaml
gcloud container binauthz policy import bin-auth-policy.yaml
```



### Task 7: Setup Pod Security Policy

```yaml
kubectl apply -f psp-restrictive.yaml
kubectl apply -f psp-role.yaml
kubectl apply -f psp-use.yaml
```

### Congratulations!
