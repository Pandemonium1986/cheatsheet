# Nexus3 : Installation et Configuration

### Version des outils

|         Os / Tool        | Version |
| :----------------------: | :-----: |
| Windows 10 Professionnel |   1803  |
|  Wsl - Debian GNU/Linux  |  9.6.0  |
|          Ansible         |   2.6+  |
|          Nexus3          | 3.15.0+ |
|          Nexus2          |  X.X.X  |

### Note en vrac

Améliration de Repository Health Check (RHC) depuis la 3.3.  

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

### Download

Denière version de nexus 3 : 3.15.0-01 (2019-01-15)
Disponible sous trois formes :

-   Archives (Unix/Windows/OSX).
-   Docker Image.
-   Cloud Templates.

### Upgradé de 2.x vers 3.y

On ne peut upgrader que d'une version 2.14.1 + vers une 3.1 +.  
On ne peut upgrader que d'une OSS vers une OSS ou d'une PRO vers une PRO.  
On ne peut upgrader que sur une version vanilla de la 3.y (fresh install).

Version recommandé pour l'upgrade 2.14.5+

### System Requirements

Avoir java 8 et un utilisateur dédié.
Augmenter la limit du nombre de fichier ouvrable par l'utilisateur nexus "nexus - nofile 65536".  
L'image docker est configuré comme il faut mais si besoin on peut la démarrer avec le flags : "--ulimit nofile=65536:65536"  
Les paramètres de la JVM sont dépendants de la RAM disponible sans toutefois dépasser les 4GB Max.
Laisser les params de la JVM par défaut à min 1200MB et max &lt;4GB.

| Physical Memory | Example Maximum Memory Configuration                        |
| --------------- | ----------------------------------------------------------- |
| 4GB             | -Xms1200M<br>-Xmx1200M<br>-XX:MaxDirectMemorySize=2G        |
| 8GB             | -Xms2703M<br><br>-Xmx2703M<br>-XX:MaxDirectMemorySize=2703M |
| 12GB            | -Xms4G<br>-Xmx4G<br>-XX:MaxDirectMemorySize=4014M           |
| 16GB            | -Xms4G<br>-Xmx4G<br>-XX:MaxDirectMemorySize=6717M           |
| 32GB            | -Xms4G<br><br>-Xmx4G<br>-XX:MaxDirectMemorySize=17530M      |
| 64GB            | -Xms4G<br>-Xmx4G<br>-XX:MaxDirectMemorySize=39158M          |

Pas de NFS pour les blobstore. Si il n'y a pas le choix il faut du NFS v4 car NFS v3 est connu pour des problèmes de compatibilités.

### Source

[Docker Sonatype/Nexus3](https://hub.docker.com/r/sonatype/nexus3)  
[Sonatype Global](https://fr.sonatype.com/)  
[Nexus3 OSS Global](https://fr.sonatype.com/nexus-repository-oss)  
[Nexus3 Dowloads](https://fr.sonatype.com/download-oss-sonatype)  
[Nexus3 Communauté](https://exchange.sonatype.com/list)
[Nexus Comparatif](https://fr.sonatype.com/nexus-repository-oss-vs.-pro-features)
