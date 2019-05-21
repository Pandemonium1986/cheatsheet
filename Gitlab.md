# Gitlab : Installation et Configuration

## Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|   Gitlab  | 11.10.4 |
|   Docker  | 18.09.5 |

## Todo

N/A

## Note en vrac

Leur idée réduire le temps passé à manager les outils et leurs interconnexions en ce concentrant sur la valeur clef : Le code source et les feature business.  

A propos de leur site web :  
Certaine fonctionnalités sont mise en avant via une page dédié comme :  
[Source Code Management](https://about.gitlab.com/product/source-code-management/)  
D'autres sont des rappels à la documentation :  
[Wiki](https://docs.gitlab.com/ee/user/project/wiki/)  
Les "missing feature" peuvent apparaître comme des épics dans gitlab :
[Design Management](https://gitlab.com/groups/gitlab-org/-/epics/370)

Tests :

-   Runners
-   Auto DevOps

## Avant propos

> GitLab is a single application that provides everything you need to Manage, Plan, Create, Verify, Package, Release, Configure, Monitor, and Secure your applications.

## About Gitlab

The entire DevOps lifecycle in one application.  
Manage -> Plan -> Create -> Verify -> Package -> Release -> Configure -> Monitor -> Secure
![Lifecycle](/img/gitlab-001.png)

### DevOps lifecycle

**Manage** : Gain visibility and insight into how your business is performing.  

_Authentication and Authorization_

-   Protected tags
-   Enforced Two-factor Authentication (2FA)

_Workflow Policies_

-   Custom header and footer system message in web and email

**Plan** : Regardless of your process, GitLab provides powerful planning tools to keep everyone synchronized.  

_Project Management_

-   Issues
-   Description Templates
-   Task Lists
-   Labels
-   Jira Integration

_Kanban Boards_

-   Project Issue Board
-   Group Issue Board

_Time Tracking_

-   Time Tracking

_Agile Portfolio Management_

-   Scrum
-   DevOps Pipeline
-   Kanban

**Create** : Create, view, and manage code and project data through powerful branching tools.  

_Source Code Management_

-   Commit graph and reporting tools
-   Task Lists
-   Discussions
-   Merge Requests
-   Protected branches
-   Private profile page
-   Merge request reviews (Premium Ultimate)
-   Git is fast
-   Git LFS 2.0 support
-   Project badges
-   Keep personal email private

_Code Review_

-   Assignee
-   Suggest changes

_Web IDE_

-   Web IDE

**Verify** : Keep strict quality standards for production code with automatic testing and reporting.  

_Continuous Integration (CI)_

-   Built-in CI/CD
-   CI/CD Horizontal Autoscaling
-   See JUnit test summaries in merge request widget
-   Free CI/CD with shared or personal Runners
-   Scheduled triggering of pipelines
-   Group-level variables

**Package** : Create a consistent and dependable software supply chain with built-in universal package management.  

_Container Registry_

-   Built-in Container Registry

**Secure** : Security capabilities, integrated into your development lifecycle.  

_SAST, DAST, Dependency Scanning, Container Scanning, License Management_

-   Ultimate feature

**Release** : GitLab's integrated CD solution allows you to ship code with zero-touch, be it on one or one thousand servers.  

_Continuous Delivery (CD)_

-   Comprehensive pipeline graphs
-   Browsable artifacts
-   Deploy Tokens

_Release Orchestration_

-   Keep track of releases using GitLab Releases
-   Environments history

_Pages_

-   Publish static websites for free with GitLab Pages

**Configure** : Configure your applications and infrastructure.  

_Kubernetes Configuration_

-   Easy Deployment of Helm, Ingress, and Prometheus on Kubernetes
-   Easy integration of existing Kubernetes clusters
-   Easy creation of Kubernetes clusters on GKE

_ChatOps_

-   Deploy from Chat
-   Create, search and view issues from chat

_Serverless_

-   Serverless
-   Serverless Monitoring

**Monitor** : Automatically monitor metrics so you know how any change in code impacts your production environment.  

_Metrics_

-   Application performance monitoring
-   GitLab server monitoring
-   Log Correlation
-   Cloud Native Monitoring

_Logging, Cluster Monitoring, Tracing_

-   Ultimate

**Defend** : Defend your apps and infrastructure from security intrusions.  

**The DevOps lifecycle cross the arguments**  
![Devops Lifecycle](/img/gitlab-002.png)

**DevOps Tools Landscape**  
![DevOps Tools Landscape](/img/gitlab-003.png)

## Procédure d'installation docker

**Quick start**  

**Advanced deployment**  

### Procédure de post-installation

## Source

[A beginner's guide to continuous integration](https://about.gitlab.com/2018/01/22/a-beginners-guide-to-continuous-integration/)  
[About](https://about.gitlab.com/)  
[Agile Planning](https://about.gitlab.com/solutions/agile-delivery/)  
[All features](https://about.gitlab.com/features/)  
[Auto DevOps](https://about.gitlab.com/product/auto-devops/)  
[Concurrent Devops](https://about.gitlab.com/concurrent-devops/)  
[Continuous Integration & Delivery](https://about.gitlab.com/product/continuous-integration/)  
[DevOps Lifeycle](https://about.gitlab.com/stages-devops-lifecycle/)  
[DevOps Tools Landscape](https://about.gitlab.com/devops-tools/)  
[DevSecOps](https://about.gitlab.com/solutions/dev-sec-ops/)  
[Handbook](https://about.gitlab.com/handbook/)  
[Resources](https://about.gitlab.com/resources/)  
[Source Code Management](https://about.gitlab.com/product/source-code-management/)  
[Status Page](https://status.gitlab.com/)  
[Value Stream Management](https://about.gitlab.com/solutions/value-stream-management/)  
