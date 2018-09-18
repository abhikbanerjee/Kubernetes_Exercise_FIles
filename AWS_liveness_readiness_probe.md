# Tutorial: Liveness and Readiness Probe

In this Tutorial you will walk through an example of evaluating the functionalities of liveness and readiness probe. 
We shall use the git repo 



## Deploy a healthy liveness and readiness probe


```
kubectl create -f helloworld-with-probes.yaml
```

Check for the pods, deployment, services and do a describe if needed

```
$ kubectl get po,deploy,svc,rs -o wide

and

$ kubectl describe deploy helloworld

```
## Deploy a Bad liveness probe example and see the consequences




## Deploy a Bad Readiness probe example and see the consequences


