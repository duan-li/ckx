# Node Affinity

 - CKA
    - Workload and Scheduling
    - Node Affinity

1. How many Labels exist on node node01?
2. Apply a label `color=blue` to node `node01`
3. Create a new deployment named blue with the nginx image and 3 replicas.
  - Name: blue
  - Replicas: 3
  - Image: nginx
4. Set Node Affinity to the deployment to place the pods on node01 only.
  - Name: blue
  - Replicas: 3
  - Image: nginx
  - NodeAffinity: requiredDuringSchedulingIgnoredDuringExecution
  - Key: color
  - value: blue
5. Create a new deployment named red with the nginx image and 2 replicas, and ensure it gets placed on the controlplane node only. Use the label key - node-role.kubernetes.io/control-plane - which is already set on the controlplane node.
  - Name: red
  - Replicas: 2
  - Image: nginx
  - NodeAffinity: requiredDuringSchedulingIgnoredDuringExecution
  - Key: node-role.kubernetes.io/control-plane
  - Use the right operator