# prose-k8s-home-ops

## Provisioning / Bootstrapping

1. Create minikube using `minikube start`.
   Pass `--subnet=''` flag to set a subnet for a cluster (>1 nodes). 

2. Bootstrap minikube with flux and load cluster config/info into bootstrapped minikube cluster using `task cluster:install`.

3. Be happy!

## Repository structure

```
/kubernetes/cluster-1/bootstrap/kustomization.yaml

/kubernetes/cluster-1/config/kustomization.yaml
/kubernetes/cluster-1/config/cluster.yaml
/kubernetes/cluster-1/config/something.yaml

/kubernetes/cluster-1/apps/default/kustomization.yaml
/kubernetes/cluster-1/apps/default/namespace.yaml
/kubernetes/cluster-1/apps/default/jellyfin/ks.yaml
/kubernetes/cluster-1/apps/default/jellyfin/app/kustomization.yaml
/kubernetes/cluster-1/apps/default/jellyfin/app/helmrelease.yaml
/kubernetes/cluster-1/apps/default/jellyfin/app/secret.sops.yaml

/kubernetes/cluster-1/apps/sockshop/kustomization.yaml
/kubernetes/cluster-1/apps/sockshop/deployment.yaml
/kubernetes/cluster-1/apps/sockshop/ingress.yaml



/kubernetes/cluster-2/bootstrap/kustomization.yaml
/kubernetes/cluster-2/config/kustomization.yaml
/kubernetes/cluster-2/config/cluster.yaml
/kubernetes/cluster-2/config/something.yaml
```