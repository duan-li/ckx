# Backup and Restore Methods

 - CKA
    - Cluster Architecture
    - Claster Maintenance
    - Backup and Restore Methods

1. What is the version of ETCD running on the cluster?
2. At what address can you reach the ETCD cluster from the controlplane node? Check the ETCD Service configuration in the ETCD POD
3. Where is the ETCD server certificate file located? Note this path down as you will need to use it later
4. Store the backup file at location /opt/snapshot-pre-boot.db
5. Luckily we took a backup. Restore the original state of the cluster using the backup file.


1. How many clusters are defined in the kubeconfig on the student-node?
2. How many nodes (both controlplane and worker) are part of cluster1?
3. How is ETCD configured for cluster1?
4. What is the IP address of the External ETCD datastore used in cluster2?
5. What is the default data directory used the for ETCD datastore used in cluster1?
6. What is the default data directory used the for ETCD datastore used in cluster2? Remember, this cluster uses an External ETCD topology.
7. How many nodes are part of the ETCD cluster that etcd-server is a part of?
8. Take a backup of etcd on cluster1 and save it on the student-node at the path /opt/cluster1.db
9. restore 