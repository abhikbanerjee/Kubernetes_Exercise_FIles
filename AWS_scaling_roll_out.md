# Scaling, Auto-Scaling and Rolling out Deployments

delete all prior pods, deployments and services

```
kubectl get o,deploy,svc -o wide
kubectl delete deploy <deploy_name>
kubectl delete pod <pod_name>
```
## Create a deployment
```
kubectl create -f https://raw.githubusercontent.com/abhikbanerjee/Kubernetes_Exercise_Files/master/helper_yaml_files/Ex_combine_deploy_service/helloworld-all.yml 
```

Check the deployments and pods
```
kubectl get po,deploy,svc -o wide
```

## Scale on an existing deployment 

Scale the deployment created in last step and see the effect on the number of pods, rs, and deployment 
```
kubectl scale deploy helloworld-all-deployment --replicas=4
```

## Use Auto-Scaling on an existing deployment 



## Functionality of Roll outs and Roll Backs

We will use the yaml files located in this section 
