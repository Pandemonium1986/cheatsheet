<!-- markdownlint-disable MD001 MD013 MD024 MD025 MD036 -->

# Ovh

## Tools versions

| Os / Tool |   Version    |
| :-------- | :----------: |
| Sles      |    15sp6     |
| Ovh       | Cloud Public |

## Intro Ovh

En tant que leader européen du cloud, nous fournissons des solutions de **cloud public** et **privé**, **d’hébergement mutualisé** et de **serveurs dédiés** dans 140 pays à travers le globe. Nous proposons également à nos clientes et clients **l’enregistrement de noms de domaine**, de la **téléphonie**, ainsi que de **l’accès à internet**. Créé en 1999, OVHcloud est une entreprise française présente dans le monde entier, grâce à la localisation internationale de ses datacenters et points de présence.

![ovh-001.png](/img/ovh-001.png)

## Produits Public Cloud

![ovh-002.png](/img/ovh-002.png)

## MoSCoW (Produits)

| Produits                   |               MoSCoW                |
| :------------------------- | :---------------------------------: |
| Compute                    | <span style="color:green">M</span>  |
| Storage                    | <span style="color:green">M</span>  |
| Network                    |  <span style="color:blue">S</span>  |
| Containers & Orchestration | <span style="color:green">M</span>  |
| Databases                  |  <span style="color:red">W</span>   |
| Analytics                  | <span style="color:orange">C</span> |
| Data Platform              |  <span style="color:red">W</span>   |
| AI & Machine learning      |  <span style="color:blue">S</span>  |
| Idam                       | <span style="color:green">M</span>  |

## MoSCoW (Services)

| Produits                   | Services                     | Options           |               MoSCoW                |
| :------------------------- | :--------------------------- | :---------------- | :---------------------------------: |
| Compute                    | Virtual Machine Instances    | General Purpose   | <span style="color:green">M</span>  |
|                            |                              | Compute Optimized | <span style="color:green">M</span>  |
|                            |                              | Memory Optimized  | <span style="color:green">M</span>  |
|                            |                              | Storage Optimized | <span style="color:green">M</span>  |
|                            |                              | Discovery         | <span style="color:green">M</span>  |
|                            | Cloud GPU                    |                   | <span style="color:green">M</span>  |
|                            | Metal Instances              |                   |  <span style="color:red">W</span>   |
|                            | Instance Backup              |                   | <span style="color:orange">C</span> |
|                            | Private Image catalog        |                   | <span style="color:green">M</span>  |
|                            | Public Image Catalog         |                   |  <span style="color:blue">S</span>  |
| Storage                    | Block Storage                | Block Storage     | <span style="color:green">M</span>  |
|                            |                              | Volume snapshot   | <span style="color:orange">C</span> |
|                            |                              | Volume Backup     | <span style="color:orange">C</span> |
|                            | Object Storage               | Standard          | <span style="color:green">M</span>  |
|                            |                              | Standard 3-AZ     | <span style="color:orange">C</span> |
|                            |                              | High Performance  | <span style="color:orange">C</span> |
|                            |                              | Standard (SWIFT)  | <span style="color:orange">C</span> |
|                            |                              | Cloud Archive     |  <span style="color:red">W</span>   |
|                            | Cold Archive                 |                   |  <span style="color:red">W</span>   |
| Network                    | Private Network              |                   | <span style="color:green">M</span>  |
|                            | Load Balancer                |                   | <span style="color:green">M</span>  |
|                            | Floating IP                  |                   | <span style="color:green">M</span>  |
|                            | Gateway                      |                   | <span style="color:green">M</span>  |
|                            | Instance Public Traffic      |                   | <span style="color:green">M</span>  |
|                            | Anti-DDoS                    |                   | <span style="color:green">M</span>  |
| Containers & Orchestration |                              |                   |                                     |
| Databases                  |                              |                   |                                     |
| Analytics                  |                              |                   |                                     |
| Data Platform              |                              |                   |                                     |
| AI & Machine learning      |                              |                   |                                     |
| Idam                       | IAM                          |                   | <span style="color:green">M</span>  |
|                            | Logs Data Platform           |                   | <span style="color:orange">C</span> |
|                            | Key Management Service (KMS) |                   | <span style="color:orange">C</span> |
|                            | Service Logs                 |                   | <span style="color:orange">C</span> |

### Compute

#### Description

Créez et exécutez facilement des VM en ligne sur une infrastructure cloud fiable et hautes performances. Faites votre choix parmi des types de machines prédéfinis ou personnalisés pour les serveurs Web, les bases de données, l'IA, etc.

#### Services

##### Virtual Machine Instances

Garantie 99.99 % sauf pour Discovery

- General Purpose: Ces instances offrent à vos serveurs de développement et vos applications web ou d'entreprise des ressources CPU/RAM équilibrées. Les vCores sont cadencés à 2 GHz et plus.
- Compute Optimized: Ces instances sont idéales pour les applications nécessitant des fréquences de calcul importantes ou de la parallélisation de tâches. Les vCores sont cadencés à 2,3 GHz et plus.
- Memory Optimized: Ces instances sont pensées pour les usages d'analyse des données et la datascience grâce à leurs ratios CPU/RAM optimisés et des IOPS accélérées. Les vCores sont cadencés à 2 GHz et plus.
- Storage Optimized: Profitez d'IOPS ultrarapides grâce à des cartes NVMe spécialement conçues pour les bases de données et les applications big data
- Discovery: Démarrez l’expérience Public Cloud avec des instances dont les ressources sont partagées, qui fourniront des performances stables à un prix très accessible.

![ovh-003.png](/img/ovh-003.png)

##### Cloud GPU

- Inférence de modèles d’IA générative pour les chatbots
- Deep learning appliqué à la vision par ordinateur
- Rendu graphique de nouvelle génération

![ovh-004.png](/img/ovh-003.png)

##### Metal Instances

- Les avantages du serveur dédié…
- …combinés avec l’automatisation du cloud
- Une maîtrise des coûts assurée
- Sécurité des données et conformité

![ovh-005.png](/img/ovh-005.png)

##### Instance Backup

À l’heure des déploiements automatisés et de « l’infrastructure as code », de nombreuses situations peuvent nécessiter une sauvegarde de votre système. Vos instances peuvent être sauvegardées à tout moment. La machine réalisera un export du disque de l’instance. Grâce à cela, vous pouvez donc industrialiser vos déploiements.

![ovh-006.png](/img/ovh-006.png)

##### Private Image catalog

Vos systèmes d'exploitation rassemblés et disponibles pour vos instances. En plus du Public Image Catalog fournissant des images système maintenues par OVHcloud, vous pouvez bâtir un Private Image Catalog pour mettre à disposition de vos instances des systèmes d'exploitation spécifiquement paramétrés pour vos usages ou des appliances fournis par un éditeur par exemple.

![ovh-007.png](/img/ovh-007.png)

##### Public Image Catalog

Les images système et applications pré-installées les plus populaires. Afin de démarrer au plus vite votre infrastructure, OVHcloud fournit les images cloud standards du marché, ainsi que les applications pré-installées les plus populaires.

![ovh-008.png](/img/ovh-008.png)

### Storage

#### Description

Le stockage cloud est un service qui permet de sauvegarder des données sur des serveurs distants accessibles via internet. Il offre la possibilité de stocker, gérer et consulter des fichiers et des données depuis n’importe quel appareil connecté à internet, à tout moment. Ce type de stockage est géré par des fournisseurs de services qui maintiennent l’infrastructure et garantissent la sécurité et la disponibilité des données. Le stockage cloud est souvent utilisé pour la sauvegarde de données, le partage de fichiers et la collaboration en ligne. Il représente une alternative flexible et évolutive au stockage traditionnel sur disque dur, sur des dispositifs de stockage locaux ou sur des serveurs dédiés

#### Services

> Note  
> Les options des service block et object storage dépendent de la région.  
> Globalement l'object storage est moins chère que le block storage.

##### Block Storage

- Sécurisé par la réplication
- Basé sur Ceph
- Performance et scalabilité au meilleur coût

##### Object Storage

- Coûts de stockage maîtrisés et optimisés
- Solution réversible et interopérable
- Résilience et haute disponibilité de vos données

![ovh-010.png](/img/ovh-010.png)

##### Cold Archive

- Stratégies de résilience à long terme
- Service compatible S3\*
- Archivage de données critiques

![ovh-012.png](/img/ovh-012.png)

### Network

#### Description

Un réseau cloud est une infrastructure virtuelle permettant de connecter appareils, services et applications via Internet en utilisant la puissance et la flexibilité des ressources cloud. Il repose sur des centres de données distants pour offrir évolutivité et gestion centralisée des ressources réseau.

#### Services

##### Private Network

Une connexion privée et flexible entre vos instances.

- Réseaux étendus entre les localisations
- Isolation
- Extension aux autres services d’OVHcloud
- Certifications ISO/IEC 27001, 27701 et HDS

##### Load Balancer

L’OVHcloud Load Balancer vous permet d’assurer plus facilement l’évolutivité, la haute disponibilité et la résilience de vos applications. Pour ce faire, la charge de trafic est répartie de manière dynamique entre plusieurs instances et régions. Améliorez l’expérience utilisateur en automatisant la gestion du trafic et de la charge, tout en maîtrisant les coûts. En combinant le Load Balancer et laFloating IP, vous pouvez créer un point d’entrée unique et sécurisé pour votre application, tout en activant des scénarios de basculement et en protégeant vos ressources privées.

- Déployable dans les régions
- Connecté aux réseaux privés
- Gestion simplifiée
- Charges de travail privées
- Intégration à l’écosystème Public Cloud
- Plusieurs protocoles de contrôle d'intégrité
- Chiffrement SSL/TLS
- Compatible avec les instances Public Cloud

![ovh-015.png](/img/ovh-015.png)

##### Floating IP

Une Floating IP est une adresse IP publique et statique qui peut être réaffectée dynamiquement à plusieurs appareils sur votre réseau, ce qui facilite la haute disponibilité, la tolérance aux pannes et le basculement pour vos applications et services dans le cloud. Ce type d’IP peut être assigné à une instance comme un Load Balancer, puis rapidement réassigné. Vous pouvez également anticiper et gérer les allocations d’IP publiques grâce à l’automatisation via API.

- Haute disponibilité
- Migration des environnements
- Point d’accès principal

![ovh-016.png](/img/ovh-016.png)

##### Gateway

Le service Gateway est le moyen le plus simple d’assurer une connexion sécurisée et évolutive entre une infrastructure vRack et un réseau connecté à Internet. Il permet un accès Internet sécurisé à toutes vos instances, sans nécessiter d'adresse IP publique séparée. Plusieurs offres sont disponibles, chacune disposant de capacités de bande passante différentes pour répondre à vos besoins spécifiques.

- Exposition flexible des services grâce aux Floating IP
- Combiner un Load Balancer et des Floating IP
- Trafic sortant vers Internet

##### Instance Public Traffic

Le trafic réseau public sortant des instances est inclus dans le prix des instances sur toutes les localisations, excepté la région Asie-Pacifique (Singapour, Sydney et Mumbai). Sur ces trois régions, 1 To/mois de trafic public sortant est inclus pour chaque projet Public Cloud. Au-delà de ce quota, chaque Go de trafic supplémentaire est facturé. Le trafic réseau entrant depuis le réseau public est inclus dans tous les cas et dans toutes les régions.

##### Anti-DDoS

Profitez d'une protection permanente sur l'ensemble de vos ressources cloud, pour garantir un niveau de service optimal

### Containers & Orchestration

#### Description

### Databases

#### Description

### Analytics

#### Description

### Data Platform

#### Description

### AI & Machine learning

#### Description

### Idam

#### Description

Identité, sécurité et opérations est une gamme de services d'OVHcloud. Ils visent à améliorer la sécurité, la gestion et l'efficacité opérationnelle de votre solution. Ces services comprennent la gestion des identités et des accès (IAM) pour le contrôle d'accès à vos données, le service de gestion de clés (KMS) pour gérer les clés de chiffrement et les journaux de service pour la surveillance des performances et de la sécurité.

#### Services

##### Gestion des identités et des accès (IAM)

Gérez de manière sécurisée l’identité de vos utilisateurs et applications, ainsi que leurs droits via une interface unique pour tous vos services.  
La solution IAM d’OVHcloud assure une gestion granulaire des accès à vos produits OVHcloud et renforce la sécurité de votre gestion des accès en s’appuyant sur une interface centralisée.

- Identité fédérée
- Unifié et harmonisé sur l’ensemble du portefeuille OVHcloud y compris pour les logiciels tiers
- Gestion fine des stratégies
- Une plus grande sécurité pour vos services
- Inclus sans frais supplémentaires

Les politiques contiennent une liste d'identités (comptes, utilisateurs, groupes d'utilisateurs) concernées par les politiques, une liste de ressources auxquelles les politiques doivent s'appliquer et une liste d'actions autorisées sur ces ressources.

![ovh-013.png](/img/ovh-013.png)

##### Logs Data Platform

Augmentez la visibilité des environnements de vos applications en collectant, traitant, analysant et stockant vos logs sur une plateforme à la fois complète et managée. L'analyse de logs est essentielle pour maintenir votre infrastructure et vos applications en bon état de fonctionnement.

- Standard et réversible
- Performante et évolutive
- Tarification complète
- Sécurité et conformité

![ovh-014.png](/img/ovh-014.png)

##### Key Management Service (KMS)

Améliorez votre sécurité et gérez efficacement vos clés de chiffrement avec le service de gestion de clés (KMS) d'OVHcloud.

Conçu pour une intégration transparente, notre KMS vous permet de gérer de manière centralisée les clés de chiffrement de toutes vos applications, qu'elles soient hébergées dans le cloud ou on-premises. Cela maximise la sécurisation des données et rationalise les opérations de sécurité.

- Protection instantanée des données grâce au chiffrement en un clic
- Sécurité renforcée avec gestion complète des accès aux clés
- Vos clés : renforcez la confidentialité des données avec Bring Your Own Keys (BYOK)
- Modèle de tarification prévisible : requêtes incluses sans frais supplémentaires
- Certification Nutanix Ready
- SDK et CLI open source

##### Service Logs (Beta)

OVHcloud Service logs vous aide à suivre « qui a fait quoi, où et quand » sur l’ensemble de vos ressources OVHcloud. Combinée à Logs Data Platform, cette solution vous permet de transformer vos logs en données précieuses à l'aide d'outils de stockage, d'archivage, d'interrogation et de visualisation. Vous pouvez désormais surveiller vos données et votre système en temps réel, pour une meilleure sécurité et une efficacité opérationnelle accrue.

- Efficacité opérationnelle accrue
- Sécurité renforcée
- Conformité sans effort
- Intégration fluide et non intrusive avec le catalogue de services OVHcloud
- Gestion unifiée des logs
- Solution open source évolutive et entièrement managée

## Local Zones

## Saving Plan

- Optimisez vos coûts avec les Savings Plans
- Évoluez à votre rythme
- Gagnez en prévisibilité
- Économisez sur vos workloads stables
- Pilotez la croissance de votre application
- Gérez la saisonnalité de votre infrastructure

![ovh-009.png](/img/ovh-009.png)

## Misc

## Qu’est-ce que le cloud computing ?

Le cloud computing est un modèle de fourniture de services informatiques qui permet aux utilisateurs d’accéder à des ressources informatiques (comme des serveurs, du stockage, des bases de données, des applications et des services réseau) via internet. Ces services sont facturés à la demande et à l’usage. Ce modèle informatique offre une flexibilité, une scalabilité et une efficacité considérables en éliminant la nécessité pour les entreprises de gérer leur propre infrastructure physique.

## Quels sont les principaux types de cloud computing ?

Il existe plusieurs types de cloud computing :

**Infrastructure-as-a-service (IaaS)** : fournit des ressources informatiques virtualisées via internet. Les utilisateurs gèrent les systèmes d’exploitation, les applications et la configuration, tandis que le fournisseur gère le matériel sous-jacent.

**Platform-as-a-service (PaaS)** : met à la disposition des utilisateurs un environnement de développement et de déploiement sur internet, ce qui leur permet de développer, exécuter et gérer des applications sans se soucier de la complexité de l’infrastructure.

**Software-as-a-service (SaaS)** : fournit des applications logicielles via internet sur un modèle d’abonnement. Les utilisateurs accèdent aux logiciels sans avoir à les installer sur leur ordinateur personnel ou sur les serveurs de l’entreprise.

## Object storage vs. block storage: How are they different?

![ovh-011.png](/img/ovh-011.png)

## Links

[Ovhcloud](https://www.ovhcloud.com/fr/)  
[Ovhcloud Blog](https://blog.ovhcloud.com/)  
[Ovhcloud Learn](https://www.ovhcloud.com/fr/learn/)  
[OVHcloud Public Cloud Doc](https://help.ovhcloud.com/csm/fr-documentation-public-cloud?id=kb_browse_cat&kb_id=574a8325551974502d4c6e78b7421938)
[OVHcloud Public Cloud Status](https://public-cloud.status-ovhcloud.com/)
