# Tutorial: Secrets

In this tutorial we will learn how to create and consume Kubernetes secrets.

Create the example application configuration file:

```
cat << EOF > config.json
{
  "username": "admin",
  "password": "123456789"
}
EOF
```

Create the `oscon` secret:

```
kubectl create secret generic oscon \
  --from-literal=username=admin \
  --from-literal=password=123456789 \
  --from-file=config.json
```

Describe the `oscon` secret: 

```
kubectl describe secrets oscon
```
We can do a -o yaml format to make sure the secret values are hashed

```
kubectl get secrets oscon -o yaml
```

Run the `secrets` job to fetch the secrets and log the secrets:

```
kubectl create -f https://raw.githubusercontent.com/kelseyhightower/secrets/master/secrets.yaml
```

View the logs of the `secrets` job:

```
kubectl get pods -a
```

This will print the logs of the pod, and we should be able to see the password and username which were set as secrets
```
kubectl logs <print-secrets-pod-name>
```
