1  k
    2  clear
    3  k run nginx-pod --image=nginx:alpine
    4  k run --help
    5  k run --help | grep tier
    6  k run messaging --image=redis:alpine -o yaml --dry-run
    7  ls
    8  k run messaging --image=redis:alpine -o yaml --dry-run > 2.yml
    9  ls
   10  mv 2.yml 2.yaml
   11  vi 2.yaml
   12  k create -f 2.yaml 
   13  k create ns --help
   14  k create ns apx-x9984574
   15  cat /opt/outputs/nodes-z3444kd9.json
   16  k get node -o json
   17  k get node -o json > /opt/outputs/nodes-z3444kd9.json
   18  cat /opt/outputs/nodes-z3444kd9.json
   19  k create svc --help
   20  k create service --help
   21  k create service clusterip --help
   22  k create service clusterip messaging-service --tcp=6379:6379 --dry-run
   23  k create service clusterip messaging-service --tcp=6379:6379 --dry-run=client
   24  k create service clusterip messaging-service --tcp=6379:6379 
   25  k create deployment --help
   26  k create deployment hr-web-app --image= (or true), warn, ignore (or false).              "true" or "strict" will use a
   27  k create deployment hr-web-app --image=kodekloud/webapp-color --replicas=2 --dry-run=client
   28  k create deployment hr-web-app --image=kodekloud/webapp-color --replicas=2
   29  k create pod --help
   30  k create pod --help
   31  k run --help
   32  k run static-busybox --image=busybox -o yaml --dry-run=client --command -- sleep 1000
   33  k run static-busybox --image=busybox --dry-run=client --command -- sleep 1000
   34  k run static-busybox --image=busybox --command -- sleep 1000
   35  k run temp-bus --image=redis:alpine
   36  k get pods
   37  k describe pod orange
   38  k get service
   39  k get deployments
   40  k edit pod orange
   41  k get pod orange -o yaml
   42  k get pod orange -o yaml > orange.yaml
   43  k delete pod orange
   44  vi orange.yaml 
   45  k create -f orange.yaml 
   46  k get pods
   47  k get pods
   48  k get pods
   49  k get pods
   50  clear
   51  ls
   52  k get svc
   53  k create svc --help
   54  k create svc nodeport --help
   55  k create svc nodeport hr-web-app-service --tcp=30082:8080
   56  k get node
   57  k get node --help
   58  jqjq
   59  jq
   60  k get node -o json
   61  k get node -o json | grep osImage
   62  k get node -o json | jq osImage
   63  k get node -o json | jq 'osImage'
   64  cat 'Ubuntu 20.04.5 LTS' > /opt/outputs/nodes_os_x43kj56.txt
   65  k create --help
   66  history