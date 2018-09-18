-- kubectl create -f daemonset.yaml and kubectl get daemonsets

-- create labels for existing nodes on minikube 

kubectl label nodes/minikube infra=development --overwrite

-- kubectl create -f daemonset-infra-development.yaml , check the kubectl get daemonsets

-- kubectl create -f daemonset-infra-prod.yaml , but checking shows all 0s as we dont have nodes with type infra=production

