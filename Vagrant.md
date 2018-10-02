# Vagrant : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|          Vagrant         |  2.1.5  |

### Procédure d'installation

La procédure d'installation de _Vagrant_ sur _Windows 10_ se déroule de la façon suivante :

Commencez par exécuter l'installeur **vagrant_2.1.5_x86_64.msi**.  

Dans la fenêtre _Welcome to the Vagrant Setup Wizard_ cliquez sur **_Next_**  
![Welcome](/img/vagrant-001.png)  

Dans la fenêtre _End-User Licence Agreement_ cochez _I  accept the terms in License Agreement_ et cliquez sur **_Next_**  
![End-User Licence Agreement](/img/vagrant-002.png)  

Dans la fenêtre _Destination Folder_ laissez par défaut et cliquez sur **_Next_**  
![Destination Folder](/img/vagrant-003.png)   

Dans la fenêtre _Ready to install Vagrant_ cliquez sur **_Install_**  
![Ready to install Vagrant](/img/vagrant-004.png)  

Dans la fenêtre _Installing Vagrant_ attendez la fin des opérations et cliquez sur  **_Next_**  
![Installing Vagrant](/img/vagrant-005.png)  

Dans la fenêtre _Completed the Vagrant Setup Wizard_ cliquez sur **_Finish_**  
![Adjusting your Path environment](/img/vagrant-006.png)  

### Procédure de post-installation

Verifying the Installation :  

```cmd
C:\Users\micha>vagrant
Usage: vagrant [options] <command> [<args>]

  -v, --version                    Print the version and exit.
  -h, --help                       Print this help.
  [...]
```

### Tutoriels Vagrant

#### Vagrant : Getting Started

##### Introduction

Vagrant is a tool for building and managing virtual machine environments in a single workflow. With an easy-to-use workflow and focus on automation, Vagrant lowers development environment setup time, increases production parity, and makes the "works on my machine" excuse a relic of the past.

##### Vagrant vs. Other Software

CLI Tools :  
Virtualization software like VirtualBox and VMware come with command line utilities for managing the lifecycle of machines on their platform. Many people make use of these utilities to write their own automation. Vagrant actually uses many of these utilities internally.  

Docker :  
Vagrant is a tool focused on providing a consistent development environment workflow across multiple operating systems. Docker is a container management that can consistently run software as long as a containerization system exists.  

Terraform :  
Vagrant and Terraform are both projects from HashiCorp. Vagrant is a tool focused for managing development environments and Terraform is a tool for building infrastructure.

##### Quickly start and try

```sh
vagrant init hashicorp/precise64
vagrant up
```

After running the above two commands, you will have a fully running virtual machine in VirtualBox running Ubuntu 12.04 LTS 64-bit. You can SSH into this machine with `vagrant ssh`, and when you are done playing around, you can terminate the virtual machine with vagrant destroy.

##### Project Setup

The first step in configuring any Vagrant project is to create a Vagrantfile. The purpose of the Vagrantfile is twofold:

-   Mark the root directory of your project. Many of the configuration options in Vagrant are relative to this root directory.

-   Describe the kind of machine and resources you need to run your project, as well as what software to install and how you want to access it.

```sh
mkdir vagrant_getting_started
cd vagrant_getting_started
vagrant init
```

##### Boxes

Boxes are added to Vagrant with vagrant box add. This stores the box under a specific name so that multiple Vagrant environments can re-use it. If you have not added a box yet, you can do so now:

```sh
vagrant box add hashicorp/precise64
```

Using a Box :  

```java
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
end

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_version = "1.1.0"
end

Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.box_url = "https://vagrantcloud.com/hashicorp/precise64"
end
```

##### Up And SSH

Boot vagrant Box :  

```sh
vagrant up
```

Ssh connection :  

```sh
vagrant ssh
```

##### Synced Folders

By default, Vagrant shares your project directory (remember, that is the one with the Vagrantfile) to the /vagrant directory in your guest machine.

```sh
$ vagrant up
...
$ vagrant ssh
...
vagrant@precise64:~$ ls /vagrant
Vagrantfile
```

##### Provisioning

Vagrant has built-in support for automated provisioning. Using this feature, Vagrant will automatically install software when you vagrant up so that the guest machine can be repeatably created and ready-to-use.

```java
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.provision :shell, path: "bootstrap.sh"
end
```

To force provisioning :

```sh
vagrant reload --provision
vagrant provision
```

##### Networking Port Forwarding

```java
Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/precise64"
  config.vm.provision :shell, path: "bootstrap.sh"
  config.vm.network :forwarded_port, guest: 80, host: 4567
end
```

##### Share

Vagrant Share lets you share your Vagrant environment to anyone around the world with an Internet connection. It will give you a URL that will route directly to your Vagrant environment from any device in the world that is connected to the Internet.

```sh
vagrant share
...
==> default: Creating Vagrant Share session...
==> default: HTTP URL: http://b1fb1f3f.ngrok.io
...
```

##### Teardown

Suspending the virtual machine by calling vagrant suspend will save the current running state of the machine and stop it.
Internet.

```sh
vagrant suspend
```

Halting the virtual machine by calling vagrant halt will gracefully shut down the guest operating system and power down the guest machine

```sh
vagrant halt
```

Destroying the virtual machine by calling vagrant destroy will remove all traces of the guest machine from your system. It'll stop the guest machine, power it down, and remove all of the guest hard disks.

```sh
vagrant destroy
```

##### Rebuild
Simply :
```sh
vagrant up
```

### Source

[Vagrant Getting Started](https://www.vagrantup.com/intro/getting-started)
