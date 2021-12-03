# kubernetes-excercise

### 1. Create service account, clusterrole, clusterrolebing. Role should have ability to create deployments, statefulset, daemonsets.
    
    kubectl apply -f storageclass.yaml
    
The above command will create **Service Account, CLusterRole & ClusterRoleBinding** with the capability of creatin **deployments, statefulset, daemonsets**

### 2. Scale a given deployment to 4 replicas.
      
    kubectl scale deployment <deployment-name> --replicas=4

The above command will scale the given replica with the count of 4

### 3. Make a node unschedulable by draining the workload.
  
    kubectl taint node node01 key=value:NoSchedule

The above command will taint to node01 with NoSchedule effect

### 4. Create a pod and schedule it on a node using node selector & label disk=ssd
 
    kubectl apply -f pod.yaml
    
The above command will schedule a pod on the node which has label of disk=ssd

### 5. Create a multi container pod, using 2 image.

    kubectl apply -f multi-container.yaml

The above command will create a pod with 2 conatiners with nginx & busybox image
