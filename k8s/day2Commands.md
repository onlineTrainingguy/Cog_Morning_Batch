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


  25  kubectl delete pods --all
   26  vi pod.yaml
   27  kubectl create -f pod.yaml
   28  kubectl get pods -o wide
   29  kubectl delete pod pod1
   30  kubectl describe node kwn1
   31  kubectl edit node kwn1
   32  kubectl get nodes --show-labels
   33  kubectl get nodes --show-labels kwn1
   34  kubectl label add nodes kwn1 env=prod
   35  kubectl label nodes kwn1 env=prod
   36  kubectl get nodes --show-labels kwn1
   37  kubectl label nodes kwn2 env=stag
   38  kubectl get nodes --show-labels kwn2
   39  vi pod.yaml
   40  kubectl create -f pod.yaml
   41  kubectl get pods -o yaml
   42  kubectl get pods -o wide
   43  kubectl delete pod pod1
   44  vi pod.yaml
   45  kubectl create -f pod.yaml
   46  kubectl get pods -o wide
   47  kubectl delete -f pod.yaml
   48  kubectl describe node kwn1
   49  kubectl describe node kwn1 | grep Taints
   50  kubectl describe node kwn2 | grep Taints
   51  kubectl describe node kmaster | grep Taints
   52  kubectl taint nodes kwn1 app=web:NoSchedule
   53  kubectl describe node kwn1 | grep Taints
   54  vi pod.yaml
   55  kubectl create -f pod.yaml
   56  kubectl get pods -o wide
   57  kubectl run pod1 --image nginx
   58  kubectl get pods -o wide
   59  kubectl run pod2 --image nginx
   60  kubectl get pods -o wide
   61  kubectl run pod3 --image nginx
   62  kubectl get pods -o wide
   63  kubectl taint nodes kwn1 app-
   64  kubectl describe node kwn1 | grep Taints
   65  kubectl run pod4 --image nginx
   66  kubectl get pods -o wide
   67  kubectl delete pods --all
   68  kubectl get pods -o wide
   69  vi rc.yaml
   70  kubectl create -f rc.yaml
   71  kubectl get rc
   72  kubectl get pods -o wide
   73  kubectl run pod1 --image nginx
   74  kubectl get pods -o wide
   75  kubectl get pods -l app=nginx-app
   76  kubectl get pods -l app==nginx-app
   77  kubectl get pods -l app!=nginx-app
   78  kubectl get pods -o wide
   79  kubectl delete pod nginx-rc-thj86
   80  kubectl get pods -o wide
   81  kubectl scale rc nginx-rc --replicas 5
   82  kubectl get pods -o wide
   83  kubectl scale rc nginx-rc --replicas 3
   84  kubectl get pods -o wide
   85  kubectl describe rc nginx-rc
   86  kubectl delete rc nginx-rc
   87  kubectl get rc
   88  kubectl get pods
   89  kubectl delete pod pod1
   90  vi pod.yaml
   91  kubectl create -f pod.yaml
   92  kubectl get pods -o wide
   93  kubectl describe rs nginx-rs
   94  kubectl get pods -l app==nginx-app
   95  kubectl get pods -l 'tier in (frontend)'
   96  kubectl delete rs nginx-rs
   97  kubectl get pods
   98  kubectl create deployment --image nginx:1.7.9 nginx-deploy --replicas 3
   99  kubectl get all
  100  kubectl create deployment --image nginx:1.7.9 nginx-deploy --replicas 3 --dry-run=client -o yaml
  101  kubectl delete deploy nginx-deployment
  102  kubectl delete deploy nginx-deploy
  103  kubectl get all
  104  vi deploy.yaml
  105  kubectl create -f deploy.yaml
  106  kubectl get all
  107  kubectl describe deploy nginx-deploy
  108  kubectl set image deploy nginx-deploy nginx-container=nginx:1.91
  109  kubectl get all
  110  kubectl rollout status deploy nginx-deploy
  111  kubectl describe deploy nginx-deploy
  112  kubectl rollout undo deploy nginx-deploy
  113  kubectl get all
  114  kubectl set image deploy nginx-deploy nginx-container=nginx:1.9.1
  115  kubectl get all
  116  kubectl describe deploy nginx-deploy
  117  kubectl get all
  118  kubectl scale deploy nginx-deploy --replicas 5
  119  kubectl get all
  120  kubectl delete deploy nginx-deploy
  121  kubectl get all
  122  history
