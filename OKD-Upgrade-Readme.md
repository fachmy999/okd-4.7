# OKD4.x Upgrade
## OKD can be upgrade from one version to another(minor/major) using the following command,

### Add below this patch command for the upstream link

oc patch clusterversion/version --patch '{"spec":{"upstream":"https://amd64.origin.releases.ci.openshift.org/graph"}}' --type=merge

### this command will display you the present version and the upgrade version which is available for your cluster.

oc adm upgrade

![image](https://user-images.githubusercontent.com/16441282/146516099-9a57ea7c-7ed9-48d7-a992-5c0d0fbe6ec9.png)

### you can upgrade the cluster to the specific version by using the command

oc adm upgrade --to=4.7.0-0.okd-2021-05-22-050008

### this will upgrade your clusteroperators and cluster version to the version 4.7.0-0.okd-2021-05-22-050008 

### you can check the history of the upgrade using the below command

oc get clusterversion -o json|jq ".items[0].status.history"
