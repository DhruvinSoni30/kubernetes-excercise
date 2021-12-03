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

### 6. Identify which node has the taint applied to it.
   
    kubectl describe node node01 | grep -i taint

The above command will identify whether the node has taint applied to it or not

### 7. Identify the node/pod has the greater memory consumption

    kubectl top pod pode_name 
    kubectl top node node_name

The above command will identify the node/pod which has the highest memory/CPU consumption

### 8. Create a daemonsets

    kubectl apply -f daemon-sets.yaml

The above command will create deamonset and 1 copy of pod will run on all the nodes
 
### 9. Create PV, PVC and attach PVC to a Pod.

    kubectl apply -f persistent-volume.yaml
    kubectl apply -f persistent-volume-claim.yaml
    kubectl apply -f pv-pod.yaml
    
The above command will create a PV, PVC and will attach PVC to a pod

### 10. Add a sidecar container busybox to a already created pod, mount a volume on it. Set shell command on that busy    box container.
    
    kubectl apply -f side.yaml

The above command will attach a new container to already created pod and also mount the volume

### 11. Find number of nodes in ready state, exclude the NoSchedule nodes. Write that number on a file.
    
    kubectl get nodes <To identify which node is in not ready state>
    kubectl describe node node01 | grep -i taint <To check whether the node has taint applied on it or not>

  
