#pod.yaml
apiVersion: v1
kind: Pod
metadata:
   name: pod1
   labels:
     app: nginx-app
spec:
   containers:
   - name: c1
     image: nginx
   - name: c2
     image: tomcat   
 
 
 1  kubectl get pods
    2  kubectl run pod1 --image nginx --dry-run=client -o yaml
    3  kubectl run pod1 --image nginx --dry-run=client -o yaml > pod.yaml
    4  cat pod.yaml
    5  la
    6  ls
    7  rm *.yaml
    8  vi pod.yaml
    9  kubectl create -f pod.yaml
   10  kubectl get pods
   11  kubectl get pods -o wide
   12  kubectl describe pod pod1
   13  vi pod.yaml
   14  kubectl apply -f pod.yaml
   15  kubectl describe pod pod1
   16  kubectl delete -f pod.yaml
   17  kubectl get pods
   18  vi pod.yaml
   19  kubectl create -f pod.yaml
   20  kubectl get pods
   21  kubectl get pods -o wide
   22  kubectl exec -it pod1 -c c1 -- bash
   23  kubectl exec -it pod1 -c c2 -- bash
