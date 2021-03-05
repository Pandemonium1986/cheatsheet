# Dans un shell admin


dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart;
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart;

==> Restart

Invoke-WebRequest -Uri "https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi" -Outfile "$Env:tmp\wsl_update_x64.msi";
msiexec /i $Env:tmp\wsl_update_x64.msi /qn;
sleep 15;
wsl --set-default-version 2;
sleep 15;
$ProgressPreference = 'SilentlyContinue';
Invoke-WebRequest -Uri https://aka.ms/wslubuntu2004 -OutFile $Env:tmp\wsl-ubuntu-2004.appx -UseBasicParsing;
Add-AppxPackage $Env:tmp\wsl-ubuntu-2004.appx;



# Choco
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'));
