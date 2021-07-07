# Prerequisites and Environment setup

## Install Docker Desktop
1. Download & Install Docker Desktop: <br />
**Windows**: https://hub.docker.com/editions/community/docker-ce-desktop-windows/ <br />
**Mac**: https://hub.docker.com/editions/community/docker-ce-desktop-mac <br />
2. Check the docker version after installation using:
    ```docker version```
## Install Kubernetes CLI
1. **Mac:**
```brew install kubectl``` or ```brew install kubernetes-cli```
2. **Windows:** Using the Chocolatey Package Manager:
    1. Open Windows Powershell as an Administrator
    2. Run the below command to Install Chocolatey Package Manager:
```Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))```
    3. Run ```choco``` to check chocolatey is successfully installed.
    4. Install Kubernetes using Chocolatey ```choco install kubernetes-cli```
    5. Test to ensure the version you installed is up to date: ```Kubectl version --client```

3. To run kubernetes cluster locally, it can be enabled from docker desktop (will not be done in the workshop due to security restrictions on SAP Laptops):
    1. Open/Run Docker App
    2. Click "Settings"
    3. On the left panel click "Kubernetes"
    4. Check ```Enable Kubernetes``` and click "Apply & Restart"
       
## Install Node.js 
1. Install NVM package Manager.
2. Install Nodejs version 12 using NVM package manager.

## Install helm 
Using chocolatey package manager: <br />
1. **Mac**: ```brew install helm```
2. **Windows**: ```choco install kubernetes-helm```

## Install Service Manger CLI v1.7.3 or higher
1. Download from https://github.com/Peripli/service-manager-cli/releases
2. Move the binary to a directory and add it in your PATH environment variable. <br />

**Mac Alternative 2:**<br />
1. Download Go from https://golang.org/doc/install
2. In the terminal run:
    1. ```export GO111MODULE=on```
    2. ```go get github.com/Peripli/service-manager-cli```
3. Go to your $Home/go/bin and rename the service-manager-cli to smctl
4. Go to your $Home and add the below to your ~/.zshrc file by replacing username with your I Number
    ```
    export GOPATH=/Users/username/go
    export PATH=$GOPATH/bin:$PATH
    ```
5. In the terminal run ```exec /bin/zsh```
6. To check the installation run ```smctl``` in the terminal.

## Install Service Catalog CLI
1. Download from: <br />      
**Mac:** https://download.svcat.sh/cli/latest/darwin/amd64/svcat or <br/>
Install using brew ```brew install kubernetes-service-catalog-client``` <br /> 
**Windows:** https://download.svcat.sh/cli/latest/windows/amd64/svcat.exe
2. Move the binary to a directory and add it in your PATH environment variable.

## Create Account in Docker Hub
Create your account in [docker hub](https://hub.docker.com/signup) (will be used in workshop to push docker images)

## Create Cloud foundry trial account
1. To create a trial account in SAP BTP, follow the tutorial [Get a Free Account on SAP BTP Trial](Get a Free Account on SAP BTP Trial) from Step 4.
2. Add "Service Manager" in your entitlements if not present. Follow the tutorial [Add a new entitlement to your Subaccount](https://developers.sap.com/tutorials/cp-cf-entitlements-add.html) to add entitlements.
