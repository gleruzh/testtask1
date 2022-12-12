# testtask1
## Setup actions
### to work with github using ssh-key
git config --global url.git@github.com:.insteadOf https://github.com/
### to work with gcloud from Arch
1. Install packages
yay -S google-cloud-sdk google-cloud-sdk-gke-gcloud-auth-plugin
2. Login to gcloud
gcloud config set account $GOOGLE-USER
gcloud auth login
3. Connect kubectl to gke cluster
gcloud container clusters get-credentials $GCP-CLUSTER --region $GCP-REGION --project $GCP-PROJECT
