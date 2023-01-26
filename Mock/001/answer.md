# 1
# 2
# 3
# 4
# 5

Run the command: kubectl expose pod messaging --port=6379 --name messaging-service

# 6
# 7

Create a pod definition file in the manifests directory. For that use command kubectl run --restart=Never --image=busybox static-busybox --dry-run=client -oyaml --command -- sleep 1000 > /etc/kubernetes/manifests/static-busybox.yaml

# 8

Run the command: kubectl run temp-bus --image=redis:alpine --namespace=finance --restart=Never

# 9

A new application orange is deployed. There is something wrong with it. Identify and fix the issue.


# 10

Run the command: kubectl expose deployment hr-web-app --type=NodePort --port=8080 --name=hr-web-app-service --dry-run=client -o yaml > hr-web-app-service.yaml to generate a service definition file.
Now, in generated service definition file add the nodePort field with the given port number under the ports section and create a service.

# 11

```
Run the command: kubectl get nodes -o jsonpath='{.items[*].status.nodeInfo.osImage}' > /opt/outputs/nodes_os_x43kj56.txt
```

# 12

```yaml

---
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-analytics
spec:
  capacity:
    storage: 100Mi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteMany
  hostPath:
      path: /pv/data-analytics
```