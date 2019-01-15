# Nexus3 : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|  Wsl - Debian GNU/Linux  |  9.6.0  |
|          Ansible         |   2.6+  |
|          Nexus3          | 3.15.0+ |
|          Nexus2          |  X.X.X  |

### Procédure d'installation

La procédure d'installation de _Nexus3_ sur _Debian 9.5.0_ se déroule de la façon suivante :

### Comparatif Nexus Artifactory ProGet

|              | Artifactory | Nexus 3 | ProGet |
| ------------ | :---------: | :-----: | :----: |
| Bower        |      X      |    X    |    X   |
| Docker       |      X      |    X    |    X   |
| GitLFS       |      X      |    X    |        |
| Maven        |      X      |    X    |    X   |
| .NET/NuGet   |      X      |    X    |    X   |
| npm          |      X      |    X    |    X   |
| PyPi         |      X      |    X    |        |
| Raw          |      X      |    X    |    X   |
| RubyGems     |      X      |    X    |    X   |
| Yum          |      X      |    X    |        |
| Apt          |      X      |    C    |        |
| Conan        |      X      |    C    |        |
| CPAN         |             |    C    |        |
| Helm         |      X      |    C    |        |
| P2           |      X      |    C    |        |
| R            |      X      |    C    |        |
| Chef         |      X      |         |        |
| CocoaPods    |      X      |         |        |
| Go           |      X      |         |        |
| Gradle       |      X      |    ?    |        |
| Ivy          |      X      |    ?    |        |
| Opkg         |      X      |         |        |
| PHP Composer |      X      |         |        |
| Puppet       |      X      |         |        |
| SBT          |      X      |         |        |
| Vagrant      |      X      |         |        |
| VCS          |      X      |         |        |
| Powershell   |             |         |    X   |
| Chocolatey   |             |         |    X   |
| Romp         |             |         |    X   |
| VSIX         |             |         |    X   |
| Upack        |             |         |    X   |

### De Nexus 2 à Nexus 3

| Fonctionnalités                       | 2.x OSS | 2.x Pro |     3.x OSS    |     3.x Pro    |
| ------------------------------------- | :-----: | :-----: | :------------: | :------------: |
| Bower                                 |         |         |        X       |        X       |
| Docker                                |         |         |        X       |        X       |
| Maven                                 |    X    |    X    |        X       |        X       |
| npm                                   |  Limité |  Limité |        X       |        X       |
| NuGet                                 |    X    |    X    |        X       |        X       |
| PyPI                                  |         |         |        X       |        X       |
| Ruby Gems                             |         |         |        X       |        X       |
| Yum                                   |    X    |    X    |        X       |        X       |
| Clusters haute disponibilité          |         |         |                |        X       |
| Plug-in S3 Blobstore                  |         |         |        X       |        X       |
| Passage de 2x à 3x                    |         |         |        X       |        X       |
| Déploiement illimité                  |    X    |    X    |        X       |        X       |
| Recherche de composants               |  Limité |    X    |        X       |        X       |
| Téléchargement artefact tiers dans IU |  Limité |  Limité |        X       |        X       |
| Repository Health Check (RHC)         |    X    |    X    |        X       |        X       |
| Métadonnées personnalisées            |         |    X    |                |      Prévu     |
| Sauvegarde et reprise améliorée       |         |         |        X       |        X       |
| API d'approvisionnement               |         |         |        X       |        X       |
| REST                                  |    X    |    X    |        X       |        X       |
| Plug-ins                              |    X    |    X    | Nexus Exchange | Nexus Exchange |
| Intégration open source               |    X    |    X    |        X       |        X       |
| Support pour jeton d'authentification |         |    X    |        X       |        X       |
| Contrôles accès personnalisés         |    X    |    X    |        X       |        X       |
| Cible Repo / Sélecteurs de contenu    |    X    |    X    |        X       |        X       |
| LDAP d'entreprise                     |         |    X    |                |        X       |
| P2                                    |         |    X    |   Communauté   |   Communauté   |
| OBR                                   |         |    X    |      Prévu     |      Prévu     |
| Crowd                                 |         |    X    |                |        X       |
| Proxy intelligent                     |         |    X    |                |      Prévu     |
| Staging et builds                     |         |    X    |                |        X       |
| Aide de la communauté                 |    X    |    X    |        X       |        X       |
| Support pour entreprises              |         |    X    |                |        X       |

### Tarifications

|              |   Artifactory  |            Nexus 3            |
| ------------ | :------------: | :---------------------------: |
| Pro          |  2950 $ par an | 10$ par utilisateurs par mois |
| Pro X        | 14400 $ par an |                               |
| Entreprise   | 29500 $ par an |                               |
| Entreprise + |      $$$$$     |                               |

Note artifactory est "Unlimited number of users"

### Note en vrac
Denière version de nexus 3 : 3.15.0-01 (2019-01-15)
Disponible sous trois formes :
* Archives (Unix/Windows/OSX).
* Docker Image.
* Cloud Templates.

### Source
[Dockersonatyper/Nexus3](https://hub.docker.com/r/sonatype/nexus3)  
[Sonatype Global](https://fr.sonatype.com/)  
[Nexus3 OSS Global](https://fr.sonatype.com/nexus-repository-oss)  
[Nexus3 Dowloads](https://fr.sonatype.com/download-oss-sonatype)  
[Nexus3 Communauté](https://exchange.sonatype.com/list)
[Nexus Comparatif](https://fr.sonatype.com/nexus-repository-oss-vs.-pro-features)
