# Install 
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# Download
brew install argocd

# Accessing locally
kubectl port-forward svc/argocd-server -n argocd 8080:443

# get admin password
argocd admin initial-password -n argocd

# Sealed Secretes
kubectl apply -f controller.yaml

# install sealed cli on operator system who has access to k8s cluster
brew install kubeseal

# Get the public key
kubeseal --fetch-cert > mycert.pem