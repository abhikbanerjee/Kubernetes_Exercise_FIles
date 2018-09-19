# Creating StatefulSets


### Create and check the StatefulSet (Zookeeper as an example here)

We shall be using the yaml files in this folder - 
https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_statefulsets

have a look at the Stateful Set file, see the various configuration for Zookeeper master , slave.

```
	$ kubectl create -f statefulset.yaml
  $ kubectl get statefulsets -o wide
```


Ref:- https://www.linkedin.com/learning/learning-kubernetes/next-steps
