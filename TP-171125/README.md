# Diagram generation
```shell
kubectl get all -o yaml | docker run -v "$(pwd)":/work -i philippemerle/kubediagrams kube-diagrams -o default-namespace.png -
```

Source : https://github.com/philippemerle/KubeDiagrams
