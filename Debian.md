# Debian 9 : Installation et Configuration

### Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|   Debian  |  9.5.0  |

### Procédure d'installation

Classique de l'install d'une vm.

### Procédure de post-installation

#### Packages

```sh
sudo apt update && sudo apt upgrade
sudo apt update && sudo apt install build-essential cowsay curl dkms dnsutils fonts-powerline git gitk htop libfortune-perl man mlocate module-assistant net-tools nmap powerline sudo tmux tree unzip vim zsh
```

#### Packages in Debian backports

```sh
sudo su -c 'echo "deb http://ftp.debian.org/debian stretch-backports main" > /etc/apt/sources.list.d/backports.list'
sudo apt -t stretch-backports install git ansible tmux
```

#### Tools

```sh
cd
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm install -g hads
sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
git clone https://github.com/jimeh/tmuxifier.git ~/.tmuxifier
```

####Configurer le réseaux

```sh
vim /etc/network/interfaces

# This file describes the network interfaces available on your system
# and how to activate them. For more information, see interfaces(5).

source /etc/network/interfaces.d/*

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
allow-hotplug enp0s3
iface enp0s3 inet dhcp

# The secondary network interface
allow-hotplug enp0s8
iface enp0s8 inet static
        address 192.168.100.12
        netmask 255.255.255.0
        getway 192.168.100.2
```
