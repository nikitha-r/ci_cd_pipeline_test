# Deploy API repository code

### 1. Docker login commands 
```bash
docker login abimtmroigbdevacr.azurecr.io

Username:
a8d3a557-09e9-4463-87cb-ae9ec61ac2a9

Password:
Pty7Q~WV6ogOViLFUFwaQVbT_vYNVKqOnEgrU
```

### 2. Docker build & push commands 
```bash
docker build -t abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest .
docker push abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest
```

### 3. Go to the azure portal
### 4. Click on app service
### 5. Click on abi-mt-mmm-gb-devv1-webapp app service
### 6. Click on deployment center on left side menu
### 7. Select the docker image tag from the drop down menu and save it
### 8. Click overview tab and restart


# Deploy JOB repository code

### 1. Docker build & push commands 
```bash
docker build -t abimtmroigbdevacr.azurecr.io/mt-mmm-be-job:latest .
docker push abimtmroigbdevacr.azurecr.io/mt-mmm-be-job:latest
```

### 2. Go to the azure portal
### 3. Click on virtual machine
### 4. Select subscription ABI GLOBAL NON-PROD
### 5. Click on abi-mt-mroi-gb-dev-bastion-vm virtual machine
### 6. Click on connect and select bastion from the dropdown menu

### 7. Login to that vm 
```bash

Username:
LinuxAdmin

Password:
l@B5fE0rE+4iV
```

### 8. Kubectl command to deploy the code
```bash
kubectl apply -f k8s/deploy.yaml
```

### 9. Kubectl command to deploy the code
```bash
kubectl get pods
kubectl logs pod/servicebus-queue-job-rkgpw-rb4jp
```

