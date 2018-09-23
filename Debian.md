Debian 9 : Installation et Configuration
======

### Version des outils
Os / Tool | Version
:---: | :---:
Debian | 9.4.0

### Procédure d'installation
Classique de l'install d'une vm.

### Procédure de post-installation
Installer les packages
```sh
apt update && apt upgrade
apt install vim sudo net-tools mlocate dnsutils ansible nmap build-essential module-assistant dkms zsh git fonts-powerline powerline
```
Configurer le réseaux
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
