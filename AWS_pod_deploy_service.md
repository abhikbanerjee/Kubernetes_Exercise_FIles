
## Practise creating Pods, Deployments and Services

Use the yaml files placed here
(https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/tree/master/helper_yaml_files/Ex_pods_deploy_svc)


# Create a deployment with the name blue  (Imperative management using config files)
```
$ kubectl create -f sample-infrastructure-with-labels.yml
```
Check the currently running pods, deployments, services and replica sets
```
 kubectl get po,deploy,svc,rs -o wide
```

Edit the Deployment and change the replicas from 1 to 2

```
# kubectl edit deploy blue
```
Check the currently running pods, deployments, services and replica sets ( we should now see 2 pods running)

```
 kubectl get po,deploy,svc,rs -o wide
```
# Use the pod.yaml file and deploy.yaml files (Examples of Imperative commands)




# One example of Declarative command (use of kubectl apply)










Ref:- 
