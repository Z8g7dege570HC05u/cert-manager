# Cert-manager

#### Заметки

CustomResourceDefinition требуется задеплоить вручную, через kubectl, т.к. k8s-handle ещё не умеет деплоить 
этот ресурс([2gis/k8s-handle#85](https://github.com/2gis/k8s-handle/issues/85)). 
```
kubectl apply -f templates/000_crds.yaml
```

PS После решения [2gis/k8s-handle#85](https://github.com/2gis/k8s-handle/issues/85) - всё равно возникает ошибка 
при деплое ресурсов

----

То, что закомментировано в config.yaml, k8s-handle ещё не умеет деплоить.
Для добавления этих ресурсов нужно:
 * Сделать `render` ресурсов и добавить их в k8s через kubectl
