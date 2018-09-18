# Tutorial: Jobs and CronJobs

In this tutorial we will learn how to create Jobs, CronJobs and inspect the containers and logs. we will use
the yaml files from this git location

https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_job_cronjob

Create a simple job 

```
kubectl create -f simplejob.yaml
```

Check for jobs, pods running

```
$ kubectl get jobs,po,svc
```

Check logs and describe the pods

```
$ kubectl describe pod <countdown-pod_name>

$ kubectl logs pod <countdown-pod_name>
```

Create a Cron Job

```

```
Check for the running cronjob,pods,svc

```

```

