## RBAC 


### Role & Rolebinding 
```  
  184  cd docker-k8s-EY-M-02-Dec-2024/
  185  ls
  186  cd 02-Kubernetes/
  187  ls
  188  mkdir 15-RBAC
  189  ls
  190  cd 15-RBAC/
  191  ls
  192  kubectl create role pod-reader --help
  193  kubectl create role pod-reader --verb=get --verb=list --verb=watch --resource=pods --dry-run -o yaml
  194  kubectl create role pod-reader --verb=get --verb=list --verb=watch --resource=pods --dry-run -o yaml > 01-Pod-Reader-Role.yaml
  195  ls
  196  kubectl get role
  197  kubectl apply -f 01-Pod-Reader-Role.yaml
  198  kubectl get role
  199  kubectl create role pod-reader-binding-amit --help
  200  kubectl create rolebinding pod-reader-binding-amit --help
  201  kubectl create rolebinding pod-reader-binding-amit --user=amit --role=pod-reader --dry-run -o yaml
  202  kubectl create rolebinding pod-reader-binding-amit --user=amit --role=pod-reader --dry-run -o yaml > 02-Pod-Reader-Rolebinding.yaml
  203  ls
  204  kubectl get role
  205  kubectl get rolebinding
  206  kubectl apply -f 02-Pod-Reader-Rolebinding.yaml
  207  s
  208  kubectl delete  -f 02-Pod-Reader-Rolebinding.yaml
  209  kubectl auth can-i get pods
  210  kubectl auth can-i get nodes
  211  kubectl auth can-i get pods --user=amit
  212  kubectl auth can-i get pods -n kube-system --user=amit
  213  kubectl apply -f 02-Pod-Reader-Rolebinding.yaml
  214  kubectl auth can-i get pods --user=amit
  215  kubectl auth can-i get pods -n kube-system --user=amit
  216  kubectl config get-contexts
  217  kubectl config use-context  amit@kind-k8s
  218  kubectl get pods
  219  kubectl config use-context  kind-k8s
  220  kubectl apply -f ../06-Deployment/01-Helloworld.yaml
  221  kubectl get pods
  222  kubectl config use-context  amit@kind-k8s
  223  kubectl get pods
  224  kubectl list pods
  225  kubectl get pods -w
  226  ls
  227  kubectl delete pods helloworld-deployment-78b46f4d6d-2n76g
  228  kubectl get deploy
```


### CluterRole & ClusterRolebindings 
```
236  kubectl get clusterroles
  237  ls
  238  kubectl config get-contexts
  239  kubectl config use-context  kind-k8s
  240  ls
  241  kubectl config get-contexts
  242  kubectl get clusterroles
  243  kubectl describe clusterroles  view
  244  ls
  245  cd 15-RBAC/
  246  s
  247  ls
  248  kubectl create clusterrolebinding view-clusterrole-binding-amit --user=amit --clusterrole=view --dry-run -o yaml
  249  kubectl create clusterrolebinding view-clusterrole-binding-amit --user=amit --clusterrole=view --dry-run -o yaml > 03-Cluster-View-Rolebinding.yaml
  250  ls
  251  kubectl apply -f 03-Cluster-View-Rolebinding.yaml
  252  kubectl auth can-i get pods -n kube-system --user=amit
  253  kubectl auth can-i get deploy  -n kube-system --user=amit
  254  kubectl auth can-i get node  -n kube-system --user=amit
  255  kubectl auth can-i get configmap  -n kube-system --user=amit
  256  kubectl config use-context  amit@kind-k8s
  257  kubectl get po
  258  kubectl get po -A
  259  kubectl get deploy  -A
  260  kubectl delete deploy helloworld-deployment
  261  kubectl config use-context  amit@kind-k8s
  262  kubectl config use-context  kind-k8s
  263  ls
  264  kubectl delete -f 03-Cluster-View-Rolebinding.yaml
  265  ls
  266  kubectl get clusterrole
  267  kubectl create clusterrolebinding clusteradmin-clusterrole-binding-amit --user=amit --clusterrole=cluster-admin --dry-run -o yaml > 04-Cluster-Admin-Rolebinding.yaml
  268  ls
  269  kubectl apply -f 04-Cluster-Admin-Rolebinding.yaml
  270  kubectl config use-context  amit@kind-k8s
  271  kubectl get nodes
  272  kubectl get deploy -A
  273  kubectl delete deploy helloworld-deployment
```
