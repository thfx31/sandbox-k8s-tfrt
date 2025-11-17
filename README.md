# TP Kubernetes Robin Thomas

## Kind (Linux)

### Install Kind
```shell
# For AMD64 / x86_64
[ $(uname -m) = x86_64 ] && curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.30.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind
```
Source: https://kind.sigs.k8s.io/docs/user/quick-start/#installation

### Create small cluster
```shell
kind create cluster --name docker-course
```

## Kubectl
### Install Kubectl
```shell
curl -LO https://dl.k8s.io/release/$(curl -Ls https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
kubectl version --client
```

### Auto completion
```shell
# Bash shell
echo "source <(kubectl completion bash)" >> ~/.bashrc
# ZSH shell
echo "source <(kubectl completion zsh)" >> ~/.zshrc
```

### Alias
```shell
# Bash shell
echo 'alias k=kubectl' >>~/.bashrc
echo 'complete -o default -F __start_kubectl k' >>~/.bashrc
# ZSH shell
echo 'alias k=kubectl' >>~/.zshrc
echo 'complete -o default -F __start_kubectl k' >>~/.zshrc
```
Source : https://kubernetes.io/fr/docs/tasks/tools/install-kubectl/
