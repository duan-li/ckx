# Taints and Tolerations

 - CKA
    - Workload and Scheduling
    - Taints and Tolerations

1. Create a taint on node01 with key of spray, value of mortein and effect of NoSchedule
2. Create another pod named bee with the nginx image, which has a toleration set to the taint mortein.
3. Remove the taint on controlplane, which currently has the taint effect of NoSchedule.