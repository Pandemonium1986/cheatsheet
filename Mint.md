# Linux Mint 19.1 : Installation et Configuration

## Version des outils

|     Os / Tool    | Version |
| :--------------: | :-----: |
| Linux Mint Tessa |   19.1  |

## Procédure d'installation

## Procédure de post-installation

### One Line installer

```sh
sudo apt install apt-transport-https build-essential ca-certificates cowsay curl dkms dnsutils fonts-powerline git gnupg2 htop libfortune-perl man mlocate module-assistant net-tools nmap powerline python-dev software-properties-common sudo tmux tree unzip vim zsh pip
```

### 7zip

```sh
sudo apt install p7zip
```

### Atom

```sh
wget -qO - https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'
sudo apt-get install atom
```

### Cryptomator

```sh
sudo add-apt-repository ppa:sebastian-stenzel/cryptomator
sudo apt-get update
sudo apt-get install cryptomator
```

### Git

```sh
add-apt-repository ppa:git-core/ppa && apt update && apt install git
```

### VirtualBox

```sh
wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] https://download.virtualbox.org/virtualbox/debian bionic contrib" > /etc/apt/sources.list.d/virtualbox.list'
sudo apt update && sudo apt-get install virtualbox-6.0
```

### Vagrant

```sh
cd ~/Téléchargements
wget https://releases.hashicorp.com/vagrant/2.2.4/vagrant_2.2.4_x86_64.deb
sudo apt install ./vagrant_2.2.4_x86_64.deb
```

### Ansible

```sh
pip install --usser molecule
```

### Signal

```sh
curl -s https://updates.signal.org/desktop/apt/keys.asc | sudo apt-key add -
echo "deb [arch=amd64] https://updates.signal.org/desktop/apt xenial main" | sudo tee -a /etc/apt/sources.list.d/signal-xenial.list
sudo apt update && sudo apt install signal-desktop
```

### Forticlient

```sh
wget -O - https://repo.fortinet.com/repo/ubuntu/DEB-GPG-KEY | sudo apt-key add -
sudo sh -c 'echo "deb [arch=amd64] https://repo.fortinet.com/repo/ubuntu/ /bionic multiverse" > /etc/apt/sources.list.d/forticlient.list'
```

### Steam

```sh
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys B05498B7
sudo sh -c 'echo "deb http://repo.steampowered.com/steam/ precise steam" > /etc/apt/sources.list.d/steam.list'
```

### Keepassxc

```sh
sudo add-apt-repository ppa:phoerious/keepassxc
sudo apt-get update
sudo apt install keepassxc
```

## Knowledge Base

## Cheat Sheet

## Source

[Battery drains](https://askubuntu.com/questions/974573/battery-drains-down-even-after-shut-down)  
[Cinnamon Settings](<https://github.com/linuxmint/Cinnamon/wiki/Backing-up-and-restoring-your-cinnamon-settings-(dconf>)  
[Cinnamon Spices](https://cinnamon-spices.linuxmint.com/)  
[Linux Mint](https://www.linuxmint.com/)  
[UFW](https://help.ubuntu.com/community/UFW)  
