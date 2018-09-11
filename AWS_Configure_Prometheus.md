# Tutorial: Collecting Metrics with Prometheus

In this Tutorial you will walk through installing Prometheus.

## Deploy Prometheus

Download the prometheus configuration file:

```
wget https://raw.githubusercontent.com/kelseyhightower/cloud-native-demo/master/configs/prometheus.yml
```

Create the prometheus configmap:

```
kubectl create configmap prometheus \
  --namespace kube-system \
  --from-file prometheus.yml
```

Create the promethues replicaset:

```
kubectl create -f https://raw.githubusercontent.com/kelseyhightower/cloud-native-demo/master/replicasets/prometheus.yaml
```

```
kubectl get pods,rs,svc -n kube-system
```

Create the prometheus service:

```
kubectl create -f https://raw.githubusercontent.com/kelseyhightower/cloud-native-demo/master/services/prometheus.yaml
```

```
kubectl get pods,svc -n kube-system 
```

```
kubectl -n kube-system port-forward <prometheus-pod-name> 9090:9090
```
See All the pods, deployments, services across all namespaces (as the Prometheus pod runs in kube-system)

```
kubectl get svc,po,deploy --all-namespaces
```
In order to Access the Prometheus UI from outside network, expose the Pod as a LoadBalancer Service 
(exposing the port 9090 to a new port)

```
kubectl expose pod <prometheus_pod_name> -n kube-system --type LoadBalancer --name prometheus-lb-service --port 9090
```

Find the LoadBalancer Port for the Service 
```
kubectl get svc,po,deploy -n kube-system
```
