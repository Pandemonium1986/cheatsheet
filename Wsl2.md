# Wsl2 : Installation et Configuration

### Tool Versions

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   20H2  |
|  Wsl - Ubuntu GNU/Linux  |   20.4  |

### Installation procedure

##### Vanilla (the hardest way)

The vanilla installation is made to free you from the use of a third party tool.  
However you must scrupulously respect the execution of the commands and the different steps (being an admin user, reboot ...).

**Step 1**

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart;
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart;
```

**Step 2**

Reboot

**Step 3**

```powershell
Invoke-WebRequest -Uri "<https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi>" -Outfile "$Env:tmp\\wsl_update_x64.msi";
msiexec /i $Env:tmp\\wsl_update_x64.msi /qn;
sleep 15;
wsl --set-default-version 2;
sleep 15;
$ProgressPreference = 'SilentlyContinue';
Invoke-WebRequest -Uri <https://aka.ms/wslubuntu2004> -OutFile $Env:tmp\\wsl-ubuntu-2004.appx -UseBasicParsing;
Add-AppxPackage $Env:tmp\\wsl-ubuntu-2004.appx;
```

##### Chocolatey (the lazy way)

```powershell
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]&#x3A;:SecurityProtocol = [System.Net.ServicePointManager]&#x3A;:SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('<https://chocolatey.org/install.ps1'>));
choco install -y wsl2 -params "/Version:2 /Retry:true"
```
