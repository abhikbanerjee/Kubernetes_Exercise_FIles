# Creating StatefulSets


### Create and check the StatefulSet (Zookeeper as an example here)

We shall be using the yaml files in this folder - 
https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_statefulsets

For this exercise have 2 parallel tabs open , so we can see the creation of pods kicked of by the creation of 
stateful sets
## In tab 1
have the get pods running with the -w option (for wait)

```
$ kubectl get pods -w -l app=zk -o wide
```
## In tab 2
have a look at the Stateful Set file, see the various configuration for Zookeeper master , slave.

```
$ kubectl create -f statefulset.yaml
$ kubectl get statefulsets -o wide
$ kubectl get pods -o wide 
```
In tab 2 , we should see zk-01 and zk-02 getting created (so it gurantees ordering and uniqueness using the <statefulset name>-<ordinal index>
  
## Now scale the stateful set to increase more replcias

```
$ kubectl scale statefulsets zk --replicas=2
```

Check the pods, statefulset, and describe the pods if you see a couple of pods are pending? What do we see the issue is?

```
$ kubectl get statefulsets -o wide
$ kubectl get pods -o wide 
```
Describe the pods created
```
$ kubectl describe pod <pod_name>  (should be zk-01, or zk-02) 
```

Ref:- https://www.linkedin.com/learning/learning-kubernetes/next-steps
