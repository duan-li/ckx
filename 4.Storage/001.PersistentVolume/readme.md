# Persistent Volume (pv)


 - CKA
    - Storage
    - Persistent Volume

1. view file in pod
2. create pod using volume
  1. Name: webapp
  2. Image Name: kodekloud/event-simulator
  3. Volume HostPath: /var/log/webapp
  4. Volume Mount: /log
3. replace pod with yaml file.
4. create pv
  * Volume Name: pv-log
  * Storage: 100Mi
  * Access Modes: ReadWriteMany
  * Host Path: /pv/log
  * Reclaim Policy: Retain
