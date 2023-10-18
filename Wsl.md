# Wsl : Installation et Configuration

## Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|  Wsl - Debian GNU/Linux  |  X.X.X  |

## Procédure d'installation

Activer le WSL de Windows 10.  
Installer Debian GNU/Linux depuis le Microsoft Store.  

## Procédure de post-installation

Installer les awesomes font sur Windows 10.  
Installer les dotfiles Pandemonium1986.  
Utiliser l'outil colortool de windows pour modifier la couleur du WSL.  

```powershell
start cmd /k "D:\Downloads\Colortool\colortool.exe -b Argonaut.itermcolors && echo Argonaut.itermcolors"
```

Configurer la console WSL comme ceci :  

Options :  
![Options](/img/wsl-001.png)  

Police :  
![Police](/img/wsl-002.png)  

Configuration :  
![Configuration](/img/wsl-003.png)  

Couleurs :  
![Couleurs](/img/wsl-004.png)  

## Activer le DrvFs

Depuis le Wsl (Cette action est à faire pour chaque sous system linux installé sur la machine Windows 10).  

```sh
sudo vim /etc/wsl.conf
```

```ini
[automount]
enabled = true
root = /mnt/
options = "metadata,uid=1000,gid=1000,umask=22,fmask=11"
mountFsTab = false
```

## Source

[Nxi - Wsl How To](https://www.nextinpact.com/news/99572-bash-ubuntu-sous-windows-10-comment-installer.htm)  
[Introducing the Windows Console Colortool](https://blogs.msdn.microsoft.com/commandline/2017/08/11/introducing-the-windows-console-colortool/)  
[iTerm Color Schemes](https://github.com/mbadolato/iTerm2-Color-Schemes)  
[Manage and configure Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/wsl-config#set-wsl-launch-settings)  
[Chmod/Chown WSL Improvements](https://blogs.msdn.microsoft.com/commandline/2018/01/12/chmod-chown-wsl-improvements/)
