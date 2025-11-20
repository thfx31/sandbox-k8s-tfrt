# Create cluster
Create cluster on Digital Ocean GUI

# Kubeconfig file
Download Kubeconfig file (Digital Ocean GUI)


# Check connectivity
```shell
kubectl --kubeconfig=./k8s-1-34-1-do-0-tf-kubeconfig.yaml get nodes
```

# Export kubeconfig
```shell
export KUBECONFIG=/home/thomas/k8-lab-DO/k8s-1-34-1-do-0-tf-kubeconfig.yaml
```

# Create namespace
```shell
kubectl create ns thomas-ns
```

# Deploy resources
```shell
# Note : Dockerhub token in secret-gitea.yml and secret-gitea-db.yml files is revoked
kubectl apply -f gitea/<resources_files.yml>
kubectl apply -f gitea-db/<resources_files.yml>
```
