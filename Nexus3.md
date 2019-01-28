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
Fonctionnalité d'analyse des licences.  

### Procédure d'installation

_Nexus 3_ est une webapps java totalement autonome. Il existe deux méthodes "d'installation" de nexus :

-   Via l'archive de distribution classique.  
    Il suffit de dézipper le contenu de l'archive (/opt/nexus) et d'exécuter bin/nexus start.
    L'application est démarré lorsque le message de log de la console "Started Sonatype Nexus".
-   Via l'image docker.  
    Exécuter la commande suivante :
    ```sh
    mkdir /some/dir/nexus-data && chown -R 200 /some/dir/nexus-data
    docker run -d -p 8081:8081 --name nexus -v /some/dir/nexus-data:/nexus-data sonatype/nexus3
    ```

### Procédure de post-installation

-   Step 1: Change the Administrative Password and Email Address
-   Step 2: Configure the SMTP Settings
-   Step 3: Configure Default HTTP and HTTPS Proxy Settings
-   Step 4: Setup a Backup procedure for your server

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

### Why Upgrade to Nexus Repository Manager 3 ?

-   Nouveau format de repository.
-   Interface utilisateur améliorée
-   Recherche de composants performante
-   Navigation dans le référentiel universel
-   Métadonnées améliorées

### Upgrade Process and Expectations

#### What Is Upgraded

Component storage format from files to blobs :  
On passe du systeme de fichier à plat de Nexus 2 au blob de Nexus 3.  
C'est le plus gros changement.  

Les metadata associées aux components passe de multiple fichier à la base OrientDB.  

Les urls de déploiement et d'accès sont maintenant différentes.  

#### What Is Not Upgraded

Parmis les plus impactant :

-   virtual repositories
-   Java VM settings, including custom system properties or variables
-   operating system nexus service scripts
-   operating system optimization, such as increasing allowable open file handles
-   environment variables affecting values used to control the repository manager
-   third-party or custom-developed plugins

#### Repository Format Support

-   npm
-   NuGet
-   Site/Raw
-   Maven2
-   RubyGems

#### Data Transfer Methods

-   HTTP Downloading
    Nécéssaire si le Nexus 2 et 3 sont sur deux machines différentes.
-   File System Copying
    Possible ssi le Nexus 2 et 3 sont configurés pour accéder au même espace de stockage.  
    C'est la méthode alernative
-   File System Hard Linking
    Possible ssi le Nexus 2 et 3 sont configurés pour accéder au même espace de stockage.  
    C'est la méthode la plus rapide.

#### Upgrade Details for Specific Elements

-   Repository IDs
    Attention les repository id n'existe plus dans Nexus 3.  
    Ils sont néanmoins "case sensitive" pendant le process de migration.
-   Repository Groups
    S'assurer que dans un groupe l'ensemble des repositories soient éligibles.  
    Au rique de ne pas upgrader le groupe entier...  
-   HTTP(S) Proxy Configuration
    Ils sont a configurer manuellement dans chaque environment.

#### Security Compatibility

-   Version 2 Roles
    Les roles sont upgradé du Nexus 2 vers le Nexus 3. Ils sont préfixé de nx2-.
-   Version 2 Repository Targets and Target Privileges
    Les Repository targets de Nexus 2 deviennent des Content Selector dans Nexus 3.

#### Upgrade Procedure

Lire la [doc officiel](https://help.sonatype.com/repomanager3/upgrading/upgrade-procedures) dans son intégralité.

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

### Repository Manager Pro Features

_Atlassian Crowd Support_  
Il s'agit d'un système de sso vendu par Atlassian. La version pro supporte nativement cette fonctionnalité.  
_Staging and Build Promotion_  
Permet d'automatiser directement au sein de Nexus3 la promotion d'artifact entre les phases de builds pour passer d'un repository de 'staging' à un repository de 'production'.  
_Tagging_  
Permet de "taguer" un ensemble d'artifact pour les associers les uns autres.  
Fonctionne de pair avec la fonctionnalité de staging de Nexus3.  
_User Token Support_  
Permet d'utiliser des token en lieu et place des mots de passes.  
_High Availability_  
Permet de clusteriser Nexus3.
_Repository Health Check_  
Fonctionnalité de check des artifacts pour notamment l'intégrer dans un pipeline DevSecOps.  
Permet de détecter automatiquement les risques de sécurité des projets opensource.  
Fonctionne "à la manière" d'un xray.  
_Customer Success_  
Coaching spécifique dédié au souscripteur.
_Enterprise Support_  
Support.

### Repository Manager Concepts

_Components_  
Le temre employé par Sonatype pour désigner un "artifact, package, bundle, archive".  
_Assets_  
Eléments constituant un composants. Par exemples un jar et son pom.xml forme un artifiact maven.  
_Components in Repositories_  
Le repository est l'endroit qui rend accéssible les composants.

### Directories

Après l'installation deux répertoires apparaissent :

-   nexus-3.XX.X-XX
    Contient l'application Nexus Repository Manager.
-   sonatype-work
    Contient l'ensemble des repositories, components et autres.
    Le dossier sonatype-work/nexus3/blobs est le plus important, c'est lui qui contient les repositories.

### Configuring the Runtime Environment

La configuration du produit se situe dans trois répertoires distinct :

-   $data-dir/etc
    Contient le fichier _nexus.properties_ qui possède quelques variables de configuration notamment l'ip et le port.
-   $install-dir/bin
    Contient le fichier _nexus.vmoptions_ qui possède quelques variables de configuration notamment la localisation du data directories.
-   $install-dir/etc
    Contient les configuration des middlexare utilisé par Nexus3.
    Pour savoir "où" modifier "quoi" autant se rendre sur la [documentation officiel](https://help.sonatype.com/repomanager3/installation/configuring-the-runtime-environment).

### Source

[Docker Sonatype/Nexus3](https://hub.docker.com/r/sonatype/nexus3)  
[Sonatype Global](https://fr.sonatype.com/)  
[Nexus3 OSS Global](https://fr.sonatype.com/nexus-repository-oss)  
[Nexus3 Dowloads](https://fr.sonatype.com/download-oss-sonatype)  
[Nexus3 Communauté](https://exchange.sonatype.com/list)
[Nexus Comparatif](https://fr.sonatype.com/nexus-repository-oss-vs.-pro-features)
[Nexus3 Run as a Service](https://help.sonatype.com/repomanager3/installation/run-as-a-service)
[Nexus3 Run Behind a Reverse Proxy](https://help.sonatype.com/repomanager3/installation/run-behind-a-reverse-proxy)
[Nexus3 Upgrade Procedures](https://help.sonatype.com/repomanager3/upgrading/upgrade-procedures)
