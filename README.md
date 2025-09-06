## Refrence Git Project
https://github.com/Benn1440/Node_Server

#### Workflow push the Application to Docker Hub so we work with the application image<br><br>
<img width="2898" height="906" alt="image" src="https://github.com/user-attachments/assets/b207d5db-d399-40b6-ba0e-c220484e0f7e" /><br><br>

## Minikube cluster for Kubernetes Operations <br><br>
<img width="855" height="240" alt="image" src="https://github.com/user-attachments/assets/733f49b2-daeb-41b1-9ea0-ba0a7a901b16" /><br><br>


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
