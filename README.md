## Reference Git Project and Official AgroCD Documentation<br><br>
https://github.com/Benn1440/Node_Server<br>
https://argo-cd.readthedocs.io/en/stable/

#### Workflow push the Application to Docker Hub so we work with the application image<br><br>
<img width="2898" height="906" alt="image" src="https://github.com/user-attachments/assets/b207d5db-d399-40b6-ba0e-c220484e0f7e" /><br><br>

#### Image available on DockerHub <br><br>
<img width="1913" height="758" alt="image" src="https://github.com/user-attachments/assets/f443c5c4-7ffb-4362-8e23-ea2f358fbbdf" /><br><br>


## Minikube cluster for Kubernetes Operations <br><br>
<img width="1152" height="420" alt="image" src="https://github.com/user-attachments/assets/23859350-55fb-4081-916b-599459c2d29d" /><br><br>

## Create namespace for ArgoCD
`kubectl create namespace argocd`

## Install ArgoCD
`kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml`

## Wait for pods to be ready
`kubectl wait --for=condition=Ready pods --all -n argocd --timeout=300s`

## Get ArgoCD admin password
`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo`

## Port forward to access ArgoCD UI
`kubectl port-forward svc/argocd-server -n argocd 8080:443`
