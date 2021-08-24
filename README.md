# Learn Terraform - Provision a GKE Cluster

This repo is a companion repo to the [Provision a GKE Cluster learn guide](https://learn.hashicorp.com/terraform/kubernetes/provision-gke-cluster), containing Terraform configuration files to provision an GKE cluster on GCP.

This sample repo also creates a VPC and subnet for the GKE cluster. This is not
required but highly recommended to keep your GKE cluster isolated.

## The steps I did

1. Clone the repository `learn-terraform-provision-gke-cluster`
2. Downgrade my terraform to the same version in `versions.tf`
    * run: `rm -r $(which terraform)`
    * install `wget`: `brew install wget`
    * install the right version using `wget`: `wget https://releases.hashicorp.com/terraform/0.14.11/terraform_0.14.11_darwin_amd64.zip`
    * then unzip the file: `unzip terraform_0.14.11_darwin_amd64.zip`
    * move the executable file to local `mv terraform /usr/local/bin/terraform`
    * finally `terraform --version` gives `Terraform v0.14.11`

> You wouldn't be able to run the terraform init if you don't have the desired version, you will run into other issues, that you wouldn't enjoy
3. Initialize terraform: `terraform init`
4. You need to setup your google cloud `application default credential` by running `gcloud auth application-default login` and login with the right account. Otherwise terraform will not be able to run the apply
5. By runnning `terraform apply` would gives you an idea about the numbe of resources will be applied, and don't forget to enable `Kubernetes Engine API` in your google cloud


This basic project, will create `vpc` and `subnet` for GKE cluster, Plus creating the GKE cluster name and host.
<img width="711" alt="Screenshot 2021-08-24 at 16 16 47" src="https://user-images.githubusercontent.com/1905513/130633469-9b218ca8-3c19-4ebc-b4de-0fc19595a0c1.png">

