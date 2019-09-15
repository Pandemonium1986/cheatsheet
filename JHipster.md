# JHipster : Installation et Configuration

## Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|  JHipster |  6.1.2  |

## Todo

N/A

## Note en vrac

Générer une application front sans gestion des utilisateurs et sans back office :  

```sh
jh app --skip-server --skip-user-management --auth jwt --db h2
```

## Avant propos

> JHipster is a development platform to generate, develop and deploy Spring Boot + Angular / React / Vue Web applications and Spring microservices.

## JHipster Quick Start

-   Install JHipster `npm install -g generator-jhipster`
-   Create a new directory and go into it `mkdir myApp && cd myApp`
-   Run JHipster and follow instructions on screen `jhipster`
-   Model your entities with JDL Studio and download the resulting `jhipster-jdl.jh` file
-   Generate your entities with `jhipster import-jdl jhipster-jdl.jh`

### Procédure de post-installation

## Source

[JHipster](https://www.jhipster.tech/)  
