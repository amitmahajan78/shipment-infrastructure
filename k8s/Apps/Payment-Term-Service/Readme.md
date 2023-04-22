# Generate base64 secret values for kafka username and password and create the secret yaml file

echo -n "<provide your value here>" | openssl enc -base64 -A

# Encrypt the secret.yaml file using sealed secret tool

kubeseal <secret.yaml >sealsecret.json

# Instal sealed secret in cluster
kubectl create -f mysealedsecret.json

# view secret
kubectl get secrets mysecret -o yaml
