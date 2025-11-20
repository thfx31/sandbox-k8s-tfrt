# Dockerhub secret
```shell
kubectl create secret docker-registry dockerhub-secret  --docker-username="thfx31" --docker-password="<dockerhub_token>"
```

# Port Forwarding
## List services
```shell
 kubectl get services
NAME          TYPE        CLUSTER-IP     EXTERNAL-IP   PORT(S)   AGE
gitea-svc     ClusterIP   10.96.184.84   <none>        81/TCP    3h23m
jenkins-svc   ClusterIP   10.96.151.3    <none>        82/TCP    3h23m
kubernetes    ClusterIP   10.96.0.1      <none>        443/TCP   9h
web-svc       ClusterIP   10.96.53.19    <none>        80/TCP    3h23m
```

## Expose services with port forwarding
```shell
kubectl port-forward services/web-svc :80
```

```shell
kubectl port-forward services/gitea-svc :81
```

```shell
kubectl port-forward services/jenkins-svc :82
```
Source : https://kubernetes.io/fr/docs/tasks/access-application-cluster/port-forward-access-application-cluster/


# Diagram generation
```shell
kubectl get all -o yaml | docker run -v "$(pwd)":/work -i philippemerle/kubediagrams kube-diagrams -o default-namespace.png -
```

Source : https://github.com/philippemerle/KubeDiagrams
