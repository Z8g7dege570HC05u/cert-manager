# Cert-manager

#### Before deploy

Deploy custom resource by kubectl, because [2gis/k8s-handle#86](https://github.com/2gis/k8s-handle/issues/86)
```
kubectl apply -f templates/000-crds.yaml
```

If you are running kubectl v1.12 or below, you will need to add the `--validate=false` flag to your `kubectl apply`
command above else you will receive a validation error relating to the `caBundle` field of the
`ValidatingWebhookConfiguration` resource. This issue is resolved in Kubernetes 1.13 onwards. More details can be found
in [kubernetes/kubernetes#69590](https://github.com/kubernetes/kubernetes/issues/69590).
```
# Create cert-manager namespace before!
# Label the cert-manager namespace to disable resource validation
kubectl label namespace cert-manager certmanager.k8s.io/disable-validation=true
```
