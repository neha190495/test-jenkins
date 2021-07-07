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

3. To run Kubernetes cluster locally, it can be enabled from docker desktop (will **not** be doing this in the workshop due to security restrictions on SAP Laptops):
    1. Open/Run Docker App
    2. Click "Settings"
    3. On the left panel click "Kubernetes"
    4. Check ```Enable Kubernetes``` and click "Apply & Restart"
       
## Install Node.js 
1. Install NVM package Manager (optional. Use nvm if you want to work with multiple Node versions in your machine)
    1. Windows Users:
        1. Download nvm-setup.zip from [nvm-windows](https://github.com/coreybutler/nvm-windows/releases)
        2. Run the downloaded installer to install nvm. If NVM doesn't appear to work immediately after installation, restart the terminal/powershell.
    2. Mac Users:
        1. Run ```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.38.0/install.sh | bash``` in your terminal to install nvm. Follow [this](https://github.com/nvm-sh/nvm) for troubleshooting issues.
2. Install Nodejs version 12.
    1. Using NVM:
        1. Run ```nvm install v12.13.0``` in cmd/terminal.
        2. Run ```nvm use v12.13.0``` in cmd/terminal.
    2. Directly without NVM:
        1. Download & install directly from [here](https://nodejs.org/dist/latest-v12.x/)
3. Verify the installation by running ```node -v``` and ```npm -v```

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
1. Download from:  
    1. **Mac:** https://download.svcat.sh/cli/latest/darwin/amd64/svcat
    2. **Windows:** https://download.svcat.sh/cli/latest/windows/amd64/svcat.exe
2. Move the binary to a directory and add it in your PATH environment variable.

**Mac Alternative 2:** <br />
Install using brew ```brew install kubernetes-service-catalog-client``` <br />

**Windows Alternative 2:** <br />
Run the below commands in powershell
```
iwr 'https://download.svcat.sh/cli/latest/windows/amd64/svcat.exe' -UseBasicParsing -OutFile svcat.exe
mkdir -f ~\bin
Move-Item -Path svcat.exe  -Destination ~\bin
$env:PATH += ";${pwd}\bin"
```
This will create a bin folder in C:\Users\<I_NO> \bin .Check if this path is added in Path environment variable.

## Create Account in Docker Hub
Create your account in [docker hub](https://hub.docker.com/signup) (will be used in workshop to push docker images)

## Create Cloud foundry trial account
1. To create a trial account in SAP BTP, follow the tutorial [Get a Free Account on SAP BTP Trial](https://developers.sap.com/tutorials/hcp-create-trial-account.html) from Step 4.
2. Add "Service Manager" in your entitlements if not present. Follow the tutorial [Add a new entitlement to your Subaccount](https://developers.sap.com/tutorials/cp-cf-entitlements-add.html) to add entitlements.
