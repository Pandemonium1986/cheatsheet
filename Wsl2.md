<!-- markdownlint-disable MD036 -->
# Wsl2 : Installation et Configuration

## Tool Versions

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   20H2  |
|  Wsl - Ubuntu GNU/Linux  |   20.4  |

## Installation procedure

### Vanilla (the hardest way)

The vanilla installation is made to free you from the use of a third party tool.  
However you must scrupulously respect the execution of the commands and the different steps (being an admin user, reboot ...).

**Step 1**

```powershell
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart;
dism.exe /online /enable-feature /featurename:VirtualM5achinePlatform /all /norestart;
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

### Chocolatey (the lazy way)

**Step 1**

```powershell
$amIAdmin = (([System.Security.Principal.WindowsIdentity]::GetCurrent()).groups -match "S-1-5-32-544");
if ( $amIAdmin )
{

  ############################`n###  Chocolatey install  ###`n############################`n";
  Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'));
  ############################`n###     Wsl2 install     ###`n############################`n";
  choco install -y wsl2 -params "/Version:2 /Retry:true";
  ############################`n###        Reboot        ###`n############################";
  restart-computer -Confirm;

}
else {
  ###############################`n###  Requires admin rights  ###`n###############################`n";
}
```

**Step 2**

Redémarrage fin d'installation du wsl

**Step 3**

```powershell
$amIAdmin = (([System.Security.Principal.WindowsIdentity]::GetCurrent()).groups -match "S-1-5-32-544");
if ( $amIAdmin )
{

  ########################`n###  Configure Wsl2  ###`n########################`n";
  wsl --set-default-version 2
  ###############################`n###  Download Linux images  ###`n###############################`n";
  $ProgressPreference = 'SilentlyContinue';
  Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile $Env:tmp\\wsl-ubuntu-2004.appx -UseBasicParsing;
  ##############################`n###  Install Linux images  ###`n##############################`n";
  Add-AppxPackage $Env:tmp\\wsl-ubuntu-2004.appx;

}
else {
  ###############################`n###  Requires admin rights  ###`n###############################`n";
}

```

**Step 4**

```powershell
$amIAdmin = (([System.Security.Principal.WindowsIdentity]::GetCurrent()).groups -match "S-1-5-32-544");
if ( $amIAdmin )
{
  ########################`n###  Vcxsrv Install   ###`n########################`n";
  choco install -y vcxsrv
  ###############################`n###  Docker desktop install  ###`n###############################`n";
  choco install -y docker-desktop
  ############################`n###        Reboot        ###`n############################";
  restart-computer -Confirm;
}
else {
  ###############################`n###  Requires admin rights  ###`n###############################`n";
}

```

## Source

[Enable Nested Virtualization In VirtualBox](https://ostechnix.com/how-to-enable-nested-virtualization-in-virtualbox)  
