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