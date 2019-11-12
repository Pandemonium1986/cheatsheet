# Azure : Overview for AZ-900

### Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|   Azure   |  X.X.X  |

## Azure ressources

### Organiser vos ressources Azure

![scope-levels](/img/az-001.png)

-   **Groupes d’administration** : Ces groupes sont des conteneurs qui vous permettent de gérer plus facilement l’accès, la stratégie et la conformité pour plusieurs abonnements. Tous les abonnements dans un groupe d’administration héritent automatiquement des conditions appliquées à ce groupe d’administration.
-   **Abonnements** : Un abonnement regroupe les comptes d’utilisateur et les ressources qui ont été créées par ces derniers. Chaque abonnement a des limites ou quotas sur la quantité de ressources que vous pouvez créer et utiliser. Les organisations peuvent utiliser des abonnements pour gérer les coûts et les ressources qui sont créées par les utilisateurs, les équipes ou les projets.
-   **Groupes de ressources** : Un groupe de ressources est un conteneur logique dans lequel les ressources Azure comme les applications web, les bases de données et les comptes de stockage sont déployées et gérées.
-   **Ressources** : les ressources sont des instances de services que vous créez, telles que des machines virtuelles, un stockage ou des bases de données SQL.

### Gérer vos coûts avec Azure Cost Management

Azure Cost Management fournit quelques fonctionnalités utiles pour prévoir et gérer les coûts :

-   **Analyser les coûts du cloud** vous aide à examiner et à analyser tous vos coûts. Vous pouvez afficher le coût agrégé pour votre compte ou tous les coûts cumulés au fil du temps.
-   **Superviser avec les budgets** vous permet de créer un budget et de configurer des alertes qui vous avertissent quand vous êtes sur le point de le dépasser.
-   **Optimiser avec des recommandations** vous aide à identifier les ressources inutilisées et sous-exploitées afin de réduire le gaspillage.
-   **Gérer les factures et les paiements** vous donne une visibilité de vos investissements dans le cloud.

### Gouvernance, sécurité et conformité dans Azure

**Azure Blueprints**  
Azure Blueprints permet aux architectes cloud et aux groupes centraux responsables des technologies de l’information de définir un ensemble reproductible de ressources Azure qui implémentent et respectent les normes, modèles et exigences d’une organisation. Azure Blueprints permet aux équipes de développement de créer et mettre en place rapidement de nouveaux environnements et d’avoir confiance en leur conformité aux exigences de l’organisation à l’aide d’un ensemble de composants intégrés, comme la mise en réseau, visant à accélérer le développement et la livraison.

**Azure Policy**  
Azure Policy est un service utilisé pour créer, attribuer et gérer des stratégies. Ces stratégies appliquent des règles à vos ressources afin qu’elles restent conformes aux standards et aux contrats de niveau de service de l’entreprise. Azure Policy analyse vos ressources pour identifier celles qui ne sont pas conformes aux stratégies que vous implémentez. Par exemple, vous pouvez disposer d’une stratégie qui n’autorise que les machines virtuelles d’une certaine taille à s’exécuter dans votre environnement. Une fois implémentée, cette stratégie évalue les machines virtuelles existantes dans votre environnement ainsi que toutes les nouvelles machines virtuelles qui y sont déployées. L’évaluation de la stratégie génère des événements de conformité que vous pouvez utiliser à des fins de supervision et de création de rapports.

**Centre de sécurité Azure**  
Azure Security Center joue un rôle important dans votre stratégie de gouvernance. Il vous aide à assurer un haut niveau de sécurité, car il :

-   Fournit une vue unifiée de la sécurité sur l’ensemble de vos charges de travail.
-   Collecte, explore et analyse les données de sécurité à partir d’un large éventail de sources, dont les pare-feu et d’autres solutions partenaires.
-   Fournit des recommandations de sécurité actionnables pour corriger les problèmes avant qu’ils ne soient exploités de façon malveillante.
-   Peut être utilisé pour appliquer des stratégies de sécurité sur l’ensemble de vos charges de travail cloud hybrides pour garantir la conformité aux normes de sécurité.

La plupart des fonctionnalités de sécurité, telles que la stratégie de sécurité et les recommandations, sont disponibles gratuitement. Certaines des fonctionnalités plus avancées, telles que l’accès aux machines virtuelles juste-à-temps et la prise en charge des charges de travail hybrides, sont disponibles au niveau standard de Security Center. L’accès aux machines virtuelles juste-à-temps peut aider à réduire la surface d’attaque du réseau en contrôlant l’accès aux ports de gestion sur les machines virtuelles Azure

### Supervision et création de rapports dans Azure

**Azure Monitor**
Azure Monitor fournit un seul hub unifié pour toutes les données de supervision et de diagnostic dans Azure. Vous pouvez l’utiliser pour obtenir une visibilité sur l’ensemble de vos ressources. Grâce à Azure Monitor, vous pouvez rechercher et résoudre les problèmes et optimiser le niveau de performance. Vous pouvez également comprendre le comportement des clients.

**Azure Service Health**
Azure Service Health fournit un affichage personnalisé de l’intégrité des services et régions Azure que vous utilisez. Service Health publie des informations sur les problèmes actuels qui sont utiles pour comprendre l’impact sur vos ressources. Des mises à jour régulières vous tiennent informé de la résolution des problèmes.

**Azure Advisor**
Azure Advisor est un conseiller personnalisé gratuit basé dans le cloud qui vous aide à suivre et à implémenter de bonnes pratiques pour les déploiements Azure. Il analyse la configuration de vos ressources et les données de télémétrie d’utilisation et suggère des solutions qui peuvent vous aider à optimiser votre environnement. Les recommandations sont divisées en quatre catégories :

-   **Haute disponibilité** : vous aide à améliorer la continuité de vos applications stratégiques. Les recommandations peuvent inclure l’ajout de machines virtuelles à un groupe à haute disponibilité ou l’ajout de points de terminaison géoredondants.
-   **Sécurité** : permet de détecter les menaces et vulnérabilités pouvant conduire à des failles de sécurité. Les recommandations peuvent inclure l’application du chiffrement des disques ou l’activation de groupes de sécurité réseau.
-   **Performances** : pour améliorer la vitesse de vos applications. Les recommandations peuvent inclure l’amélioration des niveaux de performance des requêtes SQL en créant des index ou en reconfigurant vos paramètres de gestion du trafic.
-   **Coût** : pour optimiser et réduire vos dépenses Azure globales. Les recommandations peuvent concerner le redimensionnement ou l’arrêt des machines virtuelles sous-exploitées ou encore le transfert vers des réservations Azure pour diminuer le coût total de possession.

**Centre de sécurité Azure**
Azure Security Center joue également un rôle important dans votre stratégie de supervision. Il peut vous aider à superviser la sécurité de vos machines, réseaux, systèmes de stockage, services de données et applications. Security Center fournit la détection avancée des menaces en utilisant l’apprentissage automatique et l’analytique comportementale pour aider à identifier les menaces actives ciblant vos ressources Azure. Il met également à disposition une protection contre les menaces qui bloque les programmes malveillants ou autres codes indésirables et réduit la surface d’exposition aux attaques par force brute et autres attaques réseau.

* * *

## Availability in Azure

**Availability sets**  
An availability set is a logical grouping of VMs within a datacenter that allows Azure to understand how your application is built to provide for redundancy and availability.

**Fault domains**
A fault domain is a logical group of underlying hardware that share a common power source and network switch, similar to a rack within an on-premises datacenter. As you create VMs within an availability set, the Azure platform automatically distributes your VMs across these fault domains. This approach limits the impact of potential physical hardware failures, network outages, or power interruptions.

**Update domains**
An update domain is a logical group of underlying hardware that can undergo maintenance or be rebooted at the same time. As you create VMs within an availability set, the Azure platform automatically distributes your VMs across these update domains. This approach ensures that at least one instance of your application always remains running as the Azure platform undergoes periodic maintenance. The order of update domains being rebooted may not proceed sequentially during planned maintenance, but only one update domain is rebooted at a time.

* * *

## Azure fundamentals

What is cloud computing?

-   Compute power - such as Linux servers or web applications
-   Storage - such as files and databases
-   Networking - such as secure connections between the cloud provider and your company
-   Analytics - such as visualizing telemetry and performance data

![Vm/Container/Serverless](/img/az-002.png)

Benefits of cloud computing

### Source

(Azure fundamentals)[https://docs.microsoft.com/en-us/learn/paths/azure-fundamentals/][availability options for virtual machines in azure](<https://docs.microsoft.com/fr-fr/azure/virtual-machines/linux/availability>)
