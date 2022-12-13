# testtask1

## Setup

### to work with github using ssh-key

``git config --global url.git@github.com:.insteadOf https://github.com/``
### to work with kubernetes from Arch

``yay -S kubectl kubens``
#### to work with gcloud from Arch
- Install packages

```
yay -S google-cloud-sdk google-cloud-sdk-gke-gcloud-auth-plugin
```
- Login to gcloud

```
gcloud config set account $GOOGLE_USER
gcloud auth login
```
- Connect kubectl to existing gke cluster

```
gcloud container clusters get-credentials $GCP_CLUSTER --region $GCP_REGION --project $GCP_PROJECT
```
- Or create new cluster with gcloud

```
gcloud services enable container.googleapis.com
gcloud config set compute/region $GCP_REGION
gcloud container clusters create-auto $GCP_CLUSTER
```
## Usage

- Create file with env vars (for example, ``.env``)
- export all (ex. ``source .env``)
- apply files with envsubst (ex. ``envsubst < namespace.yml | kubectl apply -f -``)

## Thanks for repo https://github.com/erickeloi/Kubernetes-Wordpress-Compass

## Change pv reclaim policy: https://kubernetes.io/docs/tasks/administer-cluster/change-pv-reclaim-policy/

no changes