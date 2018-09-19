# Creating DaemonSets


### Create and check the daemonset

We shall be using the yaml files in this folder - https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_daemonsets

```
	$ kubectl create -f daemonset.yaml 
  $ kubectl get daemonsets -o wide
```

Create labels for the existing node on the EC2

```
	$ kubectl label nodes/<IP_Address> infra=development --overwrite
```
Check if the labels shows up in the node
```
$ kubectl get nodes -o wide
```

Create a DaemonSet for the Infra-development Nodes

```
$ kubectl create -f daemonset-infra-development.yaml
```

Check if the Daemon set was created -
```
$ kubectl get daemonsets -o wide
```

Create a DaemonSet for the Infra-Production Nodes 
(but checking shows all 0s as we dont have nodes with type infra=production)

```
$ kubectl create -f daemonset-infra-prod.yaml
```
Check if the Daemon set was created -
```
$ kubectl get daemonsets -o wide
```

Ref:- https://www.linkedin.com/learning/learning-kubernetes/next-steps
