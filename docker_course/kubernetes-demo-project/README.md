1. Run: npm init -y
2. Run: npm install express
3. Install Tools
https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
Run: curl.exe -LO "https://dl.k8s.io/v1.36.0/bin/windows/amd64/kubectl.exe.sha256"
run: curl.exe -LO https://dl.k8s.io/release/v1.36.0/bin/windows/amd64/kubectl.exe
4. Run to install kubectl.exe
./kubectl.exe version --client
>>> Client Version: v1.36.0
>>> Kustomize Version: v5.8.1
5. Add path
MaxOS/Linux
In Git Bash, edit your ~/.bashrc or ~/.bash_profile and add:
    export PATH=$PATH:/c/Users/<YourUser>
Reload with:
    source ~/.bashrc

Windows:
Press Win + R, type sysdm.cpl, and hit Enter.
Go to the Advanced tab → click Environment Variables.
Edit PATH Variable
Under System variables, scroll to find Path → select it → click Edit.
Click New and paste the folder path where kubectl.exe is located.
Save and Apply
Click OK on all windows to save changes.
# check and verify the installation
Type: kubectl version --client and press Enter.
If PATH is set correctly, it should display the client version.

# Install minikube
New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
$ProgressPreference = 'SilentlyContinue'; Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing

Add Minikube to PATH
Ensure Windows can find the Minikube executable globally.
Environment Variables → System Variables → Path → Edit

Add C:\minikube to PATH
Save changes and restart PowerShell/Command Prompt

install minikube:
.\minikube

powershell
minikube start --driver=hyperv

# Verify kubectl and minikube
$ kubectl version --client
Client Version: v1.36.0
Kustomize Version: v5.8.1

$ minikube version
minikube version: v1.38.1
commit: c93a4cb9311efc66b90d33ea03f75f2c4120e9b0