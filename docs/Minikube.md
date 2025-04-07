# Minikube : Installation et Configuration

## Version des outils

|  Os / Tool | Version |
| :--------: | :-----: |
|   Debian   |  9.5.0  |
| Windows 10 |  18.03  |
| Kubernetes |  1.12.2 |
|   Kubectl  |  1.12.2 |
|  Minikube  | v0.30.0 |

## Avant propos

> Minikube is a tool that makes it easy to run Kubernetes locally. Minikube runs a single-node Kubernetes cluster inside a VM on your laptop for users looking to try out Kubernetes or develop with it day-to-day.

Minikube est une sorte de "vagrant" dédié à kubernetes. Il permet d'instancier un kubernetes d'un seul noeud via un provider virtuel.  
L'installation de Minikube fournit un simple _CLI_.
On peut :

- Instancier un cluster (de un noeud) de
- l'arréter,
- le configurer,
- si connecter etc ...  
- Y installer des modules.

Minikube n'installe pas kubenetes et n'opère pas kubenetes. Au premier minikube start celui ci va télécharger une machine virtuel choisit en fonction d'un provider et la configuré comme on le souhaite.
On manage donc la vm et la configuration du kubernetes de minikube via le cli, mais on opère le cluster via kubectl comme sur une instance classique.

La liste des providers fournit disponible pour minikube :

- virtualbox
- vmwarefusion
- KVM2
- hyperkit
- xhyve
- hyperv
- none

## Procédure d'installation

Comme expliqué précédemment minikube n'est qu'un "simple" CLI. Vous pouvez l'installer sur plusieur OS de différentes manière.  

- Via des packages binaire natif à l'os  
- En télécharchant et en éxécutant l'éxécutable

## Procédure de post-installation

Verifying the Installation :  

## Cheat Sheet

### Kubernetes Basics

| Commands | Description |
| -------- | ----------- |

### Kubernetes Essential

| Commands | Description |
| -------- | ----------- |

### Kubernetes Advanced

| Commands | Description |
| -------- | ----------- |

## Tutoriels Kubernetes

## Source

[Minikube Setup](https://kubernetes.io/docs/setup/minikube/)  
[Minikube Tutorials](https://kubernetes.io/docs/tutorials/hello-minikube/)  
[Minikube Release](https://github.com/kubernetes/minikube/releases)  
[Minikube Setup Without Vm Support](https://github.com/kubernetes/minikube#linux-continuous-integration-without-vm-support)  
[Minikube Issue 2575](https://github.com/kubernetes/minikube/issues/2575)  
[Minikube Issue 2762](https://github.com/kubernetes/minikube/issues/2762)
