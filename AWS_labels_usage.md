## Labels Usage

Create a bunch of pods with various labels, so we can operate on these pods 
(https://github.com/abhikbanerjee/Kubernetes_Exercise_Files/blob/master/helper_yaml_files/Ex_labels/sample-infrastructure-with-labels.yml)

```
# kubectl create -f sample-infrastructure-with-labels.yml
```
Let’s take a look at what we have created:

```
# kubectl get po
```
You can get more details by showing and displaying the labels:

```
# kubectl get po --show-labels
```


