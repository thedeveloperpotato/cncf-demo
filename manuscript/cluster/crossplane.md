# Create And Manage Production Kubernetes Cluster With Crossplane

TODO: Intro

## Setup

```bash
helm repo add crossplane-stable \
    https://charts.crossplane.io/stable

helm repo update

helm upgrade --install crossplane crossplane-stable/crossplane \
    --namespace crossplane-system --create-namespace --wait

kubectl apply \
    --filename crossplane-config/provider-kubernetes-incluster.yaml

kubectl apply --filename crossplane-config/config-k8s.yaml
```

## Which Cloud Provider Do You Use?

* [Google Cloud](crossplane-google.md)
* [AWS](crossplane-aws.md)
* [Azure](crossplane-azure.md)