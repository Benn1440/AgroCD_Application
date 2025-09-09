## Reference Git Project and Official ArgoCD Documentation<br><br>
https://github.com/Benn1440/pythonapp<br>
https://argo-cd.readthedocs.io/en/stable/

#### Workflow push the Application to Docker Hub so we work with the application image<br><br>
<img width="2922" height="1166" alt="image" src="https://github.com/user-attachments/assets/c291bda0-82b1-48cc-bc6b-417a3f51d479" /><br><br>

#### Image available on DockerHub <br><br>
<img width="1925" height="516" alt="image" src="https://github.com/user-attachments/assets/0cb465ad-d87f-4041-9658-6d514e97c229" />
<br><br>


## Minikube cluster for Kubernetes Operations <br><br>
<img width="1152" height="420" alt="image" src="https://github.com/user-attachments/assets/23859350-55fb-4081-916b-599459c2d29d" /><br><br>

## Create namespace for ArgoCD & Install ArgoCD
`kubectl create namespace argocd` <br><br>
`kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml`<br><br>

<img width="454" height="119" alt="image" src="https://github.com/user-attachments/assets/f3a520c7-d3a4-4453-a1ba-142673588a87" /><br><br>

<img width="1083" height="381" alt="image" src="https://github.com/user-attachments/assets/7f599cdc-b6bc-46ae-aa5e-2a11aca61503" />


## Wait for pods to be ready
`kubectl wait --for=condition=Ready pods --all -n argocd --timeout=300s`<br><br>
`kubectl get pods -n argocd`<br><br>
<img width="753" height="175" alt="image" src="https://github.com/user-attachments/assets/2342a32c-5926-4f83-9e3f-2d28eab28b7c" />


## Get ArgoCD admin password<br><br>
`kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo`<br>
<img width="950" height="177" alt="image" src="https://github.com/user-attachments/assets/f84901f6-a61e-4c14-b4a6-6e91945e31f4" />


## Port forward to access ArgoCD UI
`kubectl port-forward svc/argocd-server -n argocd 8080:443`
<img width="768" height="254" alt="image" src="https://github.com/user-attachments/assets/5a93a64f-1d1d-4ec3-ac53-a653216be53e" /><br><br>

<img width="1923" height="682" alt="image" src="https://github.com/user-attachments/assets/1cf08ca1-4249-4e08-b0b4-d442697d7f25" /><br><br>

<img width="1911" height="1040" alt="image" src="https://github.com/user-attachments/assets/a4b5b7fb-2381-485f-93ed-7772d6fc26f4" /> <br><br>

### Apply Application Configuration
Push your changes from your Local to the git repository, then run an apply to sync the  project with argocd<br><br>
`kubectl apply -f argocd-app.yaml`
<img width="1928" height="270" alt="image" src="https://github.com/user-attachments/assets/d79a8a27-4a78-44e7-9afe-2a6b55bc094a" /><br><br>

<img width="1920" height="958" alt="image" src="https://github.com/user-attachments/assets/7b6fd699-a818-43f4-a3f1-00077ec7573c" />
<br><br>

### Deployed Application and in healthy state

<img width="1925" height="958" alt="image" src="https://github.com/user-attachments/assets/c0c63d0c-1fde-4f32-a7c9-6e1c83a197aa" />





