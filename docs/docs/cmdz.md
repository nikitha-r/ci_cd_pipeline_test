## Allow the database IP

```bash
az postgres server firewall-rule create --resource-group ABI-MT-MROI-DEV-RG-Global-Non-Prod --server-name abi-mt-mroi-gb-dev-postgresdb --name AllowSingleIpAddress --start-ip-address 106.196.17.180 --end-ip-address 106.196.17.180
```

## Kubectl commands

```bash
kubectl get configmaps
kubectl get secrets
kubectl get pods
kubectl get scaledjobs
kubectl delete scaledjob scaledjob_name
kubectl delete scaledjob servicebus-queue-job 
kubectl describe pod scaledjob_name
kubectl logs pod/servicebus-queue-job-rkgpw-rb4jp
kubectl edit secrets servicebus-job-secret
kubectl get scaledjobs --all-namespaces
kubectl apply -f k8s/deploy.yaml
```

## Data IO Library 

```bash
(dockerenv) C:\Users\40103441\Desktop\projects\std\data-io-app\data1>
	typer data_io_app.py run upload_all --path C:\Users\40103441\Desktop\projects\std\data-io-app\data1\testmd

	typer data_io_app.py run download_all --path C:\Users\40103441\Desktop\projects\std\testdir

(dockerenv) C:\Users\40103441\Desktop\projects\std\mt-utils-lib\mt_utils_lib>
	typer example.py run download_all --path C:\Users\40103441\Desktop\projects\std\testdir

(dockerenv) C:\Users\40103441\Desktop\projects\std\mt-utils-lib\mt_utils_lib>
	typer example.py run upload_all --path C:\Users\40103441\Desktop\projects\std\testdir\onlyfortesting
```

#### Packaging

```bash
(okenv) C:\Users\40103441\Desktop\projects\std\check>
	poetry run check download_all
	poetry run check download_all --path C:\Users\40103441\Desktop\projects\std\testdir  
		
		Input - (\testdir can be empty, Fileshare need to have zip
		Output - (Downloads zip and extracts keeps both of it in specified \testdir  path)


(okenv) C:\Users\40103441\Desktop\projects\std\check>
	poetry run check upload_all --path C:\Users\40103441\Desktop\projects\std\testdir\testmd 
		
		Input - (testmd is folder with files in \testdir path
		Output - (Converts testmd to zip and uploads to fileshare)

C:\Users\40103441\AppData\Local\pypoetry\Cache\virtualenvs

(okenv) C:\Users\40103441\Desktop\projects\std\mt-utils-lib\mt_utils_lib>typer example.py run download_all --path C:\Users\40103441\Desktop\projects\std\testdir
```

#### Data io library errors
```bash
typer==0.3.2
typer-cli==0.0.12

Updating dependencies
Resolving dependencies...

  SolverProblemError

  Because typer-cli (0.0.12) depends on typer (>=0.3.0,<0.4.0)
   and typer (0.4.0) depends on typer (0.4.0), typer-cli (0.0.12) is incompatible with typer (0.4.0).
  And because no versions of typer match >0.4.0,<0.5.0, typer-cli (0.0.12) is incompatible with typer (>=0.4.0,<0.5.0).
  So, because mt-utils-lib depends on both typer (^0.4.0) and typer-cli (0.0.12), version solving failed.

  at c:\users\40103441\appdata\local\programs\python\python38\lib\site-packages\poetry\puzzle\solver.py:241 in _solve
      237│             packages = result.packages
      238│         except OverrideNeeded as e:
      239│             return self.solve_in_compatibility_mode(e.overrides, use_latest=use_latest)
      240│         except SolveFailure as e:
    → 241│             raise SolverProblemError(e)
      242│
      243│         results = dict(
      244│             depth_first_search(
      245│                 PackageNode(self._package, packages), aggregate_package_nodes
```
## Docker commands

```bash
docker build -t abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest .
docker push abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest

docker build -t abimtmroigbdevacr.azurecr.io/mt-mmm-be-job:latest .
docker push abimtmroigbdevacr.azurecr.io/mt-mmm-be-job:latest

docker run --rm -it abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest find /code

docker build  -f DevDockerFile  -t abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest .
docker run --env-file dev.env -p 80:80 abimtmroigbdevacr.azurecr.io/mt-mmm-be-api:latest

### Docker login commands 
docker login abimtmroigbdevacr.azurecr.io
Username:
a8d3a557-09e9-4463-87cb-ae9ec61ac2a9

Password:
Pty7Q~WV6ogOViLFUFwaQVbT_vYNVKqOnEgrU

## PAT organization
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

## PAT personal
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
git push https://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@github.com/ab-inbev-analytics/mt-mmm-ml-lib.git

## Git commands
git branch -d feat/backup-data-integration
git push origin --delete feat/backup-data-integration

Step 1: From your project repository, bring in the changes and test.

git fetch origin
git checkout -b develop origin/develop
git merge staging
Step 2: Merge the changes and update on GitHub.

git checkout staging
git merge --no-ff develop
git push origin staging

git branch -m <oldname> <newname>
git branch -m main master

git fetch origin
git branch -u origin/master master
git remote set-head origin -a


git fetch && git checkout -b wrong-branchtest
git push -u origin wrong-branchtest
```

## Loadtest

```bash
locust -f locustfile.py --headless -u 10 -r 1  --html=MMM_AKS_Report.html
```

## GRA login

```bash
url: https://globalresourceallocator.wowlabz.com/

username: china.user@abi.com
password: default@123
```

## Some links
```bash
https://akhilsharma.work/how-to-pass-environment-variables-in-azure-webapps/
https://docs.microsoft.com/en-us/azure/app-service/faq-app-service-linux#multi-container-with-docker-compose

https://github.com/nikitha-r/ci_cd_pipeline_test.git
git push https://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@github.com/nikitha-r/ci_cd_pipeline_test.git
```

## Git
### create a new repository on the command line
```bash
echo "# classic_app" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/nikitha-r/classic_app.git
git push -u origin main
```

### push an existing repository from the command line

```bash
git remote add origin https://github.com/nikitha-r/classic_app.git
git branch -M main
git push -u origin main
```