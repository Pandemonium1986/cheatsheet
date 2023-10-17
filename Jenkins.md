<!-- markdownlint-disable MD036 -->
# Jenkins : Installation et Configuration

## Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|  Jenkins  | 2.176.2 |
|   Docker  | 19.03.1 |

## Todo

N/A

## Note en vrac

Le hub docker de jenkins est divisé en deux :  

- <https://hub.docker.com/u/jenkinsci>  
- <https://hub.docker.com/u/jenkins>  

Le hub officiel est "jenkins" mais certain projet reste maintenu dans jenkinsci comme l'image "blueocean".  
La différence entre jenkins/jenkins et jenkinsci/blueocean réside dans l'installation par défaut de blueocean.

## Avant propos

> The leading open source automation server, Jenkins provides hundreds of plugins to support building, deploying and automating any project.

## Procédure d'installation docker

**Quick start**  

```sh
docker run \
  -u root \
  --rm \
  -d \
  -p 8080:8080 \
  -p 50000:50000 \
  -v jenkins-data:/var/jenkins_home \
  -v /var/run/docker.sock:/var/run/docker.sock \
  jenkinsci/blueocean
```

**Advanced deployment**  

### Procédure de post-installation

## Source

[Jenkins](https://jenkins.io/)  
[Jenkins CasC Demos](https://github.com/jenkinsci/configuration-as-code-plugin/tree/master/demos)
[Jenkins Configuration as Code Plugin](https://github.com/jenkinsci/configuration-as-code-plugin)
[Jenkins Docker GitHub](https://github.com/jenkinsci/docker)  
[Jenkins Docker](https://hub.docker.com/u/jenkins)  
[Jenkins Documentation](https://jenkins.io/doc/)  
[Jenkins Features Controlled with System Properties](https://wiki.jenkins.io/display/JENKINS/Features+controlled+by+system+properties)  
[Jenkins on Jenkins](https://ci.jenkins.io/)  
