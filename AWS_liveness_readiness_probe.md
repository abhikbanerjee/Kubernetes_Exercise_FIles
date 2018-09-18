# Tutorial: Liveness and Readiness Probe

In this Tutorial you will walk through an example of evaluating the functionalities of liveness and readiness probe. 
We shall use the git repo 

https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_liveness_readiness_probe

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

Create the deployment
```
$ kubectl create -f helloworld-with-bad-liveness-probe.yaml
```

Check for the pod, and the deployment , we should see 0 available pods, we should seethe status of the pod as "CrashLoopBackOff" after some time, and the restart counts to be increasing

```
$ kubectl get po,deploy -o wide
```

describe on deployment shows no errors, while describe on the pod shows the error description  on the pod

```
$ kubectl describe deploy helloworld-deployment-with-bad-liveness-probe

$ kubectl describe <pod/helloworld-deployment-with-bad-liveness-probe-pod_name>

```

## Deploy a Bad Readiness probe example and see the consequences

Create the deployment for bad readiness
```
$ kubectl create -f helloworld-with-bad-readiness-probe.yaml
```

Check for the pod, and the deployment , we should see 0 available pods, we should seethe status of the pod as "Running" in this case 

```
$ kubectl get po,deploy -o wide
```

though describing the pod shows the error description  on the pod

```

$ kubectl describe <pod/helloworld-deployment-with-bad-liveness-probe-pod_name>

```

