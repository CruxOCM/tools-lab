# Tools-lab
Lab for tools team

### This repo will be used to host and experimental code base before it gains maturity and ready for consumption.


## ArgoCD

### install ArgoCD in K8S

```shell
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Expose ArgoCD for external access
```shell
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'
```
*Note: HTTPS will be using self-signed certificates*

### install ArgoCD cli
```shell
brew install argocd
```

### ArgoCD API server password retrieval
```shell
argocd admin initial-password -n argocd
```

### Access ArgoCD UI/Console
```shell
kubectl port-forward svc/argocd-server -n argocd 8443:443
```