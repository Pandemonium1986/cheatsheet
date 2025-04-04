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
| Containers & Orchestration | Managed Rancher Service      |                   | <span style="color:orange">C</span> |
|                            | Managed Kubernetes Service   |                   | <span style="color:green">M</span>  |
|                            | Managed Private Registry     |                   | <span style="color:green">M</span>  |
|                            | Load Balancer for M.K.S      |                   | <span style="color:green">M</span>  |
| Databases                  | MySQL                        | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            |                              | Enterprise Plan   |  <span style="color:red">W</span>   |
|                            | PostgreSQL                   | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            |                              | Enterprise Plan   |  <span style="color:red">W</span>   |
|                            | MongoDB                      | Discovery         |  <span style="color:red">W</span>   |
|                            |                              | Production        |  <span style="color:red">W</span>   |
|                            |                              | Advanced          |  <span style="color:red">W</span>   |
|                            | Managed Caching              | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            | Cassandra                    | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            |                              | Enterprise Plan   |  <span style="color:red">W</span>   |
|                            | M3DB                         | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            |                              | Enterprise Plan   |  <span style="color:red">W</span>   |
|                            | M3 Aggregator                | Essential Plan    |  <span style="color:red">W</span>   |
|                            |                              | Business Plan     |  <span style="color:red">W</span>   |
|                            |                              | Enterprise Plan   |  <span style="color:red">W</span>   |
| Analytics                  | Data Processing              |                   |  <span style="color:red">W</span>   |
|                            | Kafka                        | Business          |  <span style="color:red">W</span>   |
|                            | Kafka                        | Enterprise        |  <span style="color:red">W</span>   |
|                            | OpenSearch                   | Essential         |  <span style="color:red">W</span>   |
|                            | OpenSearch                   | Business          |  <span style="color:red">W</span>   |
|                            | OpenSearch                   | Enterprise        |  <span style="color:red">W</span>   |
|                            | Kafka MirrorMaker            | Essential         |  <span style="color:red">W</span>   |
|                            | Kafka MirrorMaker            | Business          |  <span style="color:red">W</span>   |
|                            | Kafka MirrorMaker            | Enterprise        |  <span style="color:red">W</span>   |
|                            | Kafka Connect                | Essential         |  <span style="color:red">W</span>   |
|                            | Kafka Connect                | Business          |  <span style="color:red">W</span>   |
|                            | Kafka Connect                | Enterprise        |  <span style="color:red">W</span>   |
|                            | Managed Dashboards (Grafana) | Essential         | <span style="color:orange">C</span> |
|                            | Logs Data Platform           | Standard          |  <span style="color:blue">S</span>  |
|                            |                              | Entreprise        |  <span style="color:red">W</span>   |
| Data Platform              | Lakehouse Manager            |                   |  <span style="color:red">W</span>   |
|                            | Data Catalog                 |                   |  <span style="color:red">W</span>   |
|                            | Data Processing Engine       |                   |  <span style="color:red">W</span>   |
|                            | Analytics Manager            |                   |  <span style="color:red">W</span>   |
|                            | Applications Services        |                   |  <span style="color:red">W</span>   |
|                            | Control Center               |                   |  <span style="color:red">W</span>   |
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

Un réseau cloud est une infrastructure virtuelle permettant de connecter appareils, services et applications via internet en utilisant la puissance et la flexibilité des ressources cloud. Il repose sur des centres de données distants pour offrir évolutivité et gestion centralisée des ressources réseau.

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

Le service Gateway est le moyen le plus simple d’assurer une connexion sécurisée et évolutive entre une infrastructure vRack et un réseau connecté à internet. Il permet un accès internet sécurisé à toutes vos instances, sans nécessiter d'adresse IP publique séparée. Plusieurs offres sont disponibles, chacune disposant de capacités de bande passante différentes pour répondre à vos besoins spécifiques.

- Exposition flexible des services grâce aux Floating IP
- Combiner un Load Balancer et des Floating IP
- Trafic sortant vers internet

##### Instance Public Traffic

Le trafic réseau public sortant des instances est inclus dans le prix des instances sur toutes les localisations, excepté la région Asie-Pacifique (Singapour, Sydney et Mumbai). Sur ces trois régions, 1 To/mois de trafic public sortant est inclus pour chaque projet Public Cloud. Au-delà de ce quota, chaque Go de trafic supplémentaire est facturé. Le trafic réseau entrant depuis le réseau public est inclus dans tous les cas et dans toutes les régions.

##### Anti-DDoS

Profitez d'une protection permanente sur l'ensemble de vos ressources cloud, pour garantir un niveau de service optimal

### Containers & Orchestration

#### Description

L'orchestration de conteneurs est un processus automatisé qui permet de gérer le déploiement, la mise à l'échelle et l'administration de conteneurs applicatifs sur des environnements de serveurs multiples. Cette technique facilite le déploiement d'applications complexes réparties sur plusieurs conteneurs, assure leur fonctionnement optimal, et gère les aspects tels que la mise à jour sans interruption de service, la répartition de la charge et la résilience face aux pannes.

#### Services

##### Managed Rancher Service

Unifiez l’administration de vos clusters Kubernetes grâce à un outil managé de gestion centralisée.

- Versatilité
- Sécurité
- Scalabilité
- Support

###### Pro

- La gestion du rancher est managé
- Maitrise du déploiement des clusters k8s.
- Possibilité de déployer en mode multi cloud et/ou on premise.

###### Cons

- Cas d'usage particulié ou à raffiner.
- Il faut avoir les compétences.
- Il faut faire la M.C.O.

> Notes
>
> - Managed Rancher Service permet de faciliter la gestion de plusieurs clusters Kubernetes, dont ceux créés avec Managed Kubernetes Service.
> - Managed Kubernetes Service est un service managé pour gérer vos applications conteneurisées au sein d’un même cluster Kubernetes.
> - Ces deux services sont complémentaires, mais l’un ne nécessite pas obligatoirement l’utilisation de l’autre.
>   Vous pouvez gérer manuellement vos clusters Kubernetes créés avec Managed Kubernetes Service sans utiliser Managed Rancher Service. À l’inverse, vous pouvez utiliser Managed Rancher Service pour gérer des clusters Kubernetes autres que ceux créés avec Managed Kubernetes Service, par exemple, des clusters Kubernetes sur des serveurs Bare Metal OVHcloud ou bien chez d’autres fournisseurs de cloud (sur site ou non).
> - Vous pouvez gérer n’importe quel cluster Kubernetes (chez OVHcloud, d’autres fournisseurs de cloud ou sur site) via Managed Rancher Service.

##### Managed Kubernetes Service

Libérez-vous de l’installation et de la maintenance de vos clusters Kubernetes et déployez rapidement vos applications grâce à la solution d’orchestration de conteneurs de référence.

- Gestion intégrale par OVHcloud
- Interopérabilité
- Écosystème de services
- Évolutivité et résilience

###### Pro

- La gestion du cluster est managé.

###### Cons

- Limité à ce que supporte le cloud opérateur (CSI/CNI/Version de k8s).

##### Managed Private Registry

Stockez, gérez et accédez facilement à vos images de conteneurs et Helm charts grâce à ce service entièrement géré.

- Interopérabilité complète.
- Sécurité maximale.
- Tarifs prévisibles.
- Conformité en matière d'hébergement de données de santé.

###### Pro

- Nous avons besoin d'un registry privé accessible depuis le cloud afin de déployer nos applications.

###### Cons

- N/A.

> Notes
>
> - L'hébergement d'un registre privé de conteneurs nécessite un environnement sécurisé pour le stockage de vos images de conteneurs. Pour ce faire, vous pouvez soit utiliser un service d'un fournisseur de cloud, installer des logiciels tiers sur votre propre infrastructure ou créer votre propre solution personnalisée.
> - Utiliser le service d'un fournisseur de cloud, tel que Managed Private Registry d'OVHcloud, constitue la solution la plus simple pour héberger un registre privé de conteneurs. Ce service entièrement géré vous libère du stress lié à la maintenance de votre registre privé, tout en offrant une sécurité élevée, des tarifs prévisibles et une gamme de fonctionnalités.

##### Load Balancer for M.K.S

Gérez les variations d’activité en répartissant le trafic sur vos différentes ressources.  
Équilibrez la charge de votre application en temps réel sur plusieurs nœuds de manière automatique et sécurisée.

- 99,99 % de disponibilité
- Gestion automatique des nœuds
- Intégré directement à Kubernetes
- Conforme et certifié

### Databases

#### Description

Une base de données cloud est souvent appelée « Database as a Service » ou « Cloud database Service ». Elle est conçue et accessible via une plateforme cloud. Le cloud permet aux entreprises d'héberger des bases de données sans acheter de matériel dédié. Les bases de données cloud prennent en charge à la fois les bases de données relationnelles (MySQL , PostgreSQL) et NoSQL (MongoDB, Caching, Apache Cassandra).

#### Services

##### MySQL

Bénéficiez d’un service 100 % managé pour déployer et opérer les bases de données MySQL de vos sites e-commerce et de vos applications. Nous nous chargeons de la gestion de votre service.

##### PostgreSQL

Déployez un cluster managé PostgreSQL en quelques clics. Bénéficiez du moteur de bases de données relationnelles open-source de référence pour vos données et vos applications.

##### MongoDB

Accélérez votre time to market en nous confiant l’administration de vos bases de données NoSQL. Laissez vos équipes se concentrer sur leur cœur de métier et le développement de vos services. Nous nous occupons de la configuration, de la maintenance, de la sauvegarde, de la sécurité et du monitoring de votre moteur de base de données NoSQL orienté documents préféré.

##### Managed Caching

Votre service « in-memory database » NoSQL compatible Redis® OSS et managée par OVHcloud. Améliorez la vitesse d'exécution de vos applications grâce à une solution de caching haut performance

##### Cassandra

Déployez et exécutez un cluster distribué Apache Cassandra en quelques clics, managé par nos équipes. Très performant et hautement disponibilité, ce service NoSQL est spécialement adapté pour vos traitements massifs de requêtes en écriture.

##### M3DB

Déployez un moteur de base de données time series (TSBD) open source, distribué et performant. Un service 100% managé idéal pour collecter vos métriques à petite ou grande échelle en un instant.

##### M3 Aggregator

Déployez une architecture M3 Aggregator dédiée à l'agrégation de flux pour vos bases de données M3DB. Intégrez vos flux directement à vos workflows de métriques, en fonction de critères prédéfinis.

### Analytics

#### Description

Le cloud analytics désigne l’utilisation de services d’analyse de données hébergés sur des plateformes cloud. Cette approche permet de traiter et d’analyser de grandes quantités de données en utilisant des ressources informatiques cloud fournies et gérées par des tiers. Elle offre évolutivité, efficacité et réduction des coûts liés à l’infrastructure informatique.

![ovh-017.png](/img/ovh-017.png)

#### Services

##### Data Processing

Analysez vos données rapidement et en toute simplicité sur Apache Spark. OVHcloud se charge de déployer en quelques minutes un cluster Apache Spark dédié pour traiter votre requête.

- Parallélisation des traitements.
- Vous codez, nous déployons.
- Réduction des coûts.
- Sécurité et conformité.

##### Kafka

Déployez en quelques clics un cluster Apache Kafka complet et managé par nos équipes, tout en conservant le contrôle de vos données.

##### OpenSearch

Le moteur NoSQL d’indexation, de recherche de contenu et d’analyse de données entièrement managé par nos soins. Simplifiez le quotidien de vos développeurs en leur permettant de se concentrer sur la création d’applications.

##### Kafka MirrorMaker

Copiez et streamez facilement les données entre deux clusters Apache Kafka. Service 100% managé pour maintenir une replication complète dans un datacenter distant et une haute disponibilité de vos clusters Kafka.

##### Kafka Connect

Kafka Connect permet de connecter des systèmes externes à un cluster Apache Kafka. Plus besoin de vous préoccuper de la gestion matérielle du service : configuration, monitoring et mises à jour.

##### Managed Dashboards (Grafana)

Créez des tableaux de bord et des graphiques dynamiques depuis différentes sources avec la plateforme Grafana®.

- Open-source et managé
- Rapport performances/prix
- Sécurité et conformité
- Plus de 60 services Public Cloud

![ovh-017.png](/img/ovh-017.png)

###### Pro

- La gestion du dashboard est managé.

###### Cons

- Pricing élevé pour le service rendu.
- A étudier face aux grafana(s) fournient par les autres services.

![ovh-018.png](/img/ovh-018.png)

##### Logs Data Platform

Augmentez la visibilité des environnements de vos applications en collectant, traitant, analysant et stockant vos logs sur une plateforme à la fois complète et managée. L'analyse de logs est essentielle pour maintenir votre infrastructure et vos applications en bon état de fonctionnement.

- Standard et réversible
- Performante et évolutive
- Tarification complète
- Sécurité et conformité

![ovh-019.png](/img/ovh-019.png)

###### Pro

- Une plateforme complète entierement managé.
- Plateforme offerte en "standard".

###### Cons

- Pricing flous ...
- Beaucoup d'options flous ...

### Data Platform

#### Description

Une plateforme collaborative unifiée pour intégrer, stocker massivement, préparer et exploiter vos données, afin d'accélérer vos projets Data & Analytics.

![ovh-020.png](/img/ovh-020.png)

![ovh-021.png](/img/ovh-021.png)

#### Services

##### Lakehouse Manager

Un service serverless de data lake et data warehouse sur OVHcloud Data Platform, utilisant Apache Iceberg pour le stockage massif de données.

##### Data Catalog

Référentiel central pour la gestion de toutes les sources de données de OVHcloud Data Platform : connectez-les, analysez-les et ajoutez des règles de planification pour définir des normes de formatage.

##### Data Processing Engine

Service d'intégration et de transformation des données de OVHcloud Data Platform, pour automatiser l’exécution et l’orchestration de vos workflows ETL/ELT en production.

##### Analytics Manager

Service de visualisation de données et de gestion des requêtes de OVHcloud Data Platform. Faites vos analyses en libre-service, réalisez vos tableaux de bord, et facilitez les prises de décisions en vous appuyant sur vos données.

##### Applications Services

Service de conception et déploiement d’API et de web apps personnalisées. Développez vos API et partagez des tableaux de bord détaillés avec OVHcloud Data Platform.

##### Control Center

Gérez les droits d'accès et accédez en temps réel aux informations de votre infrastructure. Obtenez une vue d’ensemble complète de vos pipelines de données, applications et connecteurs afin de collecter des métriques, surveiller les performances et configurer des alertes.

### AI & Machine learning

#### Description

#### Services

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

### Qu’est-ce que le cloud computing ?

Le cloud computing est un modèle de fourniture de services informatiques qui permet aux utilisateurs d’accéder à des ressources informatiques (comme des serveurs, du stockage, des bases de données, des applications et des services réseau) via internet. Ces services sont facturés à la demande et à l’usage. Ce modèle informatique offre une flexibilité, une scalabilité et une efficacité considérables en éliminant la nécessité pour les entreprises de gérer leur propre infrastructure physique.

### Quels sont les principaux types de cloud computing ?

Il existe plusieurs types de cloud computing :

**Infrastructure-as-a-service (IaaS)** : fournit des ressources informatiques virtualisées via internet. Les utilisateurs gèrent les systèmes d’exploitation, les applications et la configuration, tandis que le fournisseur gère le matériel sous-jacent.

**Platform-as-a-service (PaaS)** : met à la disposition des utilisateurs un environnement de développement et de déploiement sur internet, ce qui leur permet de développer, exécuter et gérer des applications sans se soucier de la complexité de l’infrastructure.

**Software-as-a-service (SaaS)** : fournit des applications logicielles via internet sur un modèle d’abonnement. Les utilisateurs accèdent aux logiciels sans avoir à les installer sur leur ordinateur personnel ou sur les serveurs de l’entreprise.

### Object storage vs. block storage: How are they different?

![ovh-011.png](/img/ovh-011.png)

### Qu’est-ce qu’un registre privé de conteneurs ?

Un registre privé de conteneurs est un système de stockage et de distribution pour les images de conteneurs, c'est-à-dire des fichiers qui incluent tout le code, les bibliothèques et les autres ressources nécessaires pour exécuter une application dans un environnement conteneurisé. Accessible uniquement aux utilisateurs autorisés, un registre de conteneurs privé constitue un espace sécurisé pour stocker les images de conteneurs. Il permet aux organisations de gérer et de contrôler facilement leurs images de conteneurs, tout en offrant une intégration simple avec les workflows existants d'intégration continue et de déploiement continu (CI/CD) pour un développement, des tests et un déploiement d'applications fluides.

### Qu’est-ce que le data processing ?

Le data processing, ou traitement des données, désigne le processus d’analyse des données brutes. En effet, ces vastes quantités d’informations s’avèrent capitales pour les entreprises. Une fois traitées, elles permettent une meilleure compréhension des chiffres de ventes, de l’efficacité d’une campagne marketing ou encore d’un risque financier. Cette opération s’articule en plusieurs étapes :

- La collecte des données. La quantité d’informations recueillies influence la qualité du résultat. Elles peuvent provenir de différentes sources : fichiers client, inventaires, études antérieures, etc. Pour être utilisables, elles doivent être fiables
- La préparation des informations. Il s’agit d’une phase de « nettoyage » de vos bases de données. Elle vise à éliminer les éléments de mauvaise qualité et/ou les erreurs.
- L’importation des données travaillées et le démarrage du traitement. L’automatisation de cette analyse passe par un algorithme de machine learning.
- L’interprétation des données. Cette étape vous permet de dégager des informations lisibles et exploitables par tous.
- Le stockage des données. Il sert à conserver des données qui pourront servir lors de futures études.

Notez que le stockage d’informations est soumis à certaines réglementations. Par exemple, le RGPD exige une solution sécurisée et conforme pour l’ensemble de vos données.

## Links

[Ovhcloud](https://www.ovhcloud.com/fr/)  
[Ovhcloud Blog](https://blog.ovhcloud.com/)  
[Ovhcloud Learn](https://www.ovhcloud.com/fr/learn/)  
[OVHcloud Public Cloud Doc](https://help.ovhcloud.com/csm/fr-documentation-public-cloud?id=kb_browse_cat&kb_id=574a8325551974502d4c6e78b7421938)
[OVHcloud Public Cloud Status](https://public-cloud.status-ovhcloud.com/)
