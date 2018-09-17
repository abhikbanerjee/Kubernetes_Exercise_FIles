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
-- add a label on an existing pod and delete the label  -- 

kubectl label po/helloworld app=helloworldapp --overwrite

kubectl label po/helloworld app-  (remove the label)

kubectl create -f sample-infrastructure-with-labels.yml (creates a bunch of pods with labels)

-- use selectors to search in labels to pull out pods, and delete them

-- kubectl get pods --selector env=production --show-labels

-- kubectl get pods -l env=production,dev-lead=amy --show-labels  (equal to)

-- kubectl get pods -l env=production,dev-lead!=amy --show-labels  (not equal to)

-- kubectl get pods -l 'release-version in (1.0,2.0)' --show-labels (use the in operator)

-- kubectl get pods -l 'release-version notin (1.0,2.0)' --show-labels

-- kubectl delete pods -l dev-lead=karthik (delete pods with a specific label, works for deployment, replication set)

