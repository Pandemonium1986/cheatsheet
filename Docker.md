Docker : Installation et Configuration
======

### Version des outils
Os / Tool | Version
:---: | :---:
CentOs | 7.4.1708
Docker Ce | 17.12.0

### Avant propos
Docker is available in two editions: Community Edition (CE) and Enterprise Edition (EE).  
Docker Community Edition (CE) is ideal for developers and small teams looking to get started with Docker and experimenting with container-based apps. Docker CE has two update channels, stable and edge:
* Stable gives you reliable updates every quarter
* Edge gives you new features every month

### Procédure d'installation
La procédure d'installation de _Docker_ sur _CentOs 7_ se déroule de la façon suivante :
Installez les prérequis.
```sh
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```
Assurez-vous qu'ils n'existent aucune autres versions de _Docker_ sur la machine.
```sh
sudo yum remove docker docker-common docker-selinux docker-engine
```
Assurez-vous que le repository _extras_ est bien activé.
```sh
sudo yum-config-manager --enable extras
```
Ajoutez le repository _Docker_.
```sh
sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
Installez et vérifiez que _Docker_ fonctionne correctement.
```sh
sudo yum install docker-ce
sudo systemctl start docker
sudo docker run hello-world
```

### Procédure de post-installation
Vérifiez les versions de _Docker_ disponible et celle installée.
```sh
yum list docker-ce --showduplicates | sort -r
```
Ajouter un utilisateur non _sudoers_ qui aura les privilège d'utiliser _Docker_.
```sh
sudo groupadd docker
sudo usermod -aG docker $USER
```
Activer _Docker_ au démarrage de Linux.
```sh
sudo systemctl enable docker
```

### Docker concepts
A container runs natively on Linux and shares the kernel of the host machine with other containers. It runs a discrete process, taking no more memory than any other executable, making it lightweight.  
By contrast, a virtual machine (VM) runs a full-blown “guest” operating system with virtual access to host resources through a hypervisor. In general, VMs provide an environment with more resources than most applications need.  

Container | Vms
:---: | :---:
![Container](/img/dck-001.png) | ![Vms](/img/dck-002.png)

### Tutoriels Dockers
#### Docker : Get Started
##### Part 1 Orientation
**Ce qu'il faut retenir :**  
Un simple `docker run nom-de-l'image` permet de "tirer" une image depuis un repository et de "démarrer" un container.  
Un container est l'instanciation d'une image.  
Pour manager les containers on utilise la commande `docker container`.  
Pour manager les images on utilise la commande `docker image` manage les images.  

**Cheat sheet :**   
```
## List Docker CLI commands
docker
docker container --help

## Display Docker version and info
docker --version
docker version
docker info

## Excecute Docker image
docker run hello-world

## List Docker images
docker image ls

## List Docker containers (running, all, all in quiet mode)
docker container ls
docker container ls --all
docker container ls -a -q
```
##### Part 2 Containers
**Ce qu'il faut retenir :**  
Pour créer un container on doit le builder depuis fichier nommé _Dockerfile_.  
Pour construire une image on utilise la commande `docker build`.  
Une image construite en local est disponible via la commande `docker image ls`  
Pour partager une image on commence par la taguer via `docker tag image username/repository:tag`  
On la push ensuite sur un repository via `docker push username/repository:tag`  

**Cheat sheet :**  
```
docker build -t friendlyhello .                  # Create image using this directory's Dockerfile
docker run -p 4000:80 friendlyhello              # Run "friendlyname" mapping port 4000 to 80
docker run -d -p 4000:80 friendlyhello           # Same thing, but in detached mode
docker container ls                              # List all running containers
docker container ls -a                           # List all containers, even those not running
docker container stop <hash>                     # Gracefully stop the specified container
docker container kill <hash>                     # Force shutdown of the specified container
docker container rm <hash>                       # Remove specified container from this machine
docker container rm $(docker container ls -a -q) # Remove all containers
docker image ls -a                               # List all images on this machine
docker image rm <image id>                       # Remove specified image from this machine
docker image rm $(docker image ls -a -q)         # Remove all images from this machine
docker login                                     # Log in this CLI session using your Docker credentials
docker tag <image> username/repository:tag       # Tag <image> for upload to registry
docker push username/repository:tag              # Upload tagged image to registry
docker run username/repository:tag               # Run image from a registry
```
##### Part 3 Services
**Ce qu'il faut retenir :**  
Un service est un container codifié par un fichier _docker-compose.yml_ qui définit comment il doit être instancié.  
Un fichier _docker-compose.yml_ se déploie via la commande `docker stack deploy -c docker-compose.yml nom_de_service`.  
Pour pouvoir déployer une _stack_ il faut instancier un cluster _Swarm_ (Minimun un node).
On instancie un cluster _Swarm_ avec la commande `docker swarm init`.  
Pour manager les services on utilise la commande  `docker service`.  

**Cheat sheet :**  
```
docker stack ls                                  # List stacks or apps
docker stack deploy -c <composefile> <appname>   # Run the specified Compose file
docker service ls                                # List running services associated with an app
docker service ps <service>                      # List tasks associated with an app
docker inspect <task or container>               # Inspect task or container
docker container ls -q                           # List container IDs
docker stack rm <appname>                        # Tear down an application
docker swarm leave --force                       # Take down a single node swarm from the manager
```
##### Part 4 Swarms
**Ce qu'il faut retenir :**  
Un _Swarm_ est un ensemble de machine qui forment un cluster docker.  
On initialise un _Swarm_ avec la commande `docker swarm init`  
Celle ci retourne un id qui permet aux autres instances de rejoindre le cluster _Swarm_ via la commande `docker swarm join --token SWMTKN-1-sha256 @ip_du_master:2377`  
_Swarm_ embarque tout un tas de service natif comme un load balanceur, simplifiant la scalabilité et la configuration d'application en mode distribué.

**Cheat sheet :**  
```
docker-machine create --driver virtualbox myvm1                                                     # Create a VM (Mac, Win7, Linux)
docker-machine create -d hyperv --hyperv-virtual-switch "myswitch" myvm1                            # Win10
docker-machine env myvm1                                                                            # View basic information about your node
docker-machine ssh myvm1 "docker node ls"                                                           # List the nodes in your swarm
docker-machine ssh myvm1 "docker node inspect <node ID>"                                            # Inspect a node
docker-machine ssh myvm1 "docker swarm join-token -q worker"                                        # View join token
docker-machine ssh myvm1                                                                            # Open an SSH session with the VM; type "exit" to end
docker node ls                                                                                      # View nodes in swarm (while logged on to manager)
docker-machine ssh myvm2 "docker swarm leave"                                                       # Make the worker leave the swarm
docker-machine ssh myvm1 "docker swarm leave -f"                                                    # Make master leave, kill swarm
docker-machine ls                                                                                   # list VMs, asterisk shows which VM this shell is talking to
docker-machine start myvm1                                                                          # Start a VM that is currently not running
docker-machine env myvm1                                                                            # show environment variables and command for myvm1
eval $(docker-machine env myvm1)                                                                    # Mac command to connect shell to myvm1
& "C:\Program Files\Docker\Docker\Resources\bin\docker-machine.exe" env myvm1 | Invoke-Expression   # Windows command to connect shell to myvm1
docker stack deploy -c <file> <app>                                                                 # Deploy an app; command shell must be set to talk to manager (myvm1), uses local Compose file
docker-machine scp docker-compose.yml myvm1:~                                                       # Copy file to node's home dir (only required if you use ssh to connect to manager and deploy the app)
docker-machine ssh myvm1 "docker stack deploy -c <file> <app>"                                      # Deploy an app using ssh (you must have first copied the Compose file to myvm1)
eval $(docker-machine env -u)                                                                       # Disconnect shell from VMs, use native docker
docker-machine stop $(docker-machine ls -q)                                                         # Stop all running VMs
docker-machine rm $(docker-machine ls -q)                                                           # Delete all VMs and their disk images
```

##### Part 5 Stacks
**Ce qu'il faut retenir :**  
Une _Stack_ est définit comme suit : A stack is a group of interrelated services that share dependencies, and can be orchestrated and scaled together. A single stack is capable of defining and coordinating the functionality of an entire application (though very complex applications may want to use multiple stacks).   
Ajouter un _service_ dans une _Stack_ revient à ajouter un payload dans la partie services du fichier _docker-compose.yml_.
```yaml
version: "3"
services:
  web:
    # replace username/repo:tag with your name and image details
    image: username/repo:tag
    deploy:
      replicas: 5
      restart_policy:
        condition: on-failure
      resources:
        limits:
          cpus: "0.1"
          memory: 50M
    ports:
      - "80:80"
    networks:
      - webnet
  visualizer:
    image: dockersamples/visualizer:stable
    ports:
      - "8080:8080"
    volumes:
      - "/var/run/docker.sock:/var/run/docker.sock"
    deploy:
      placement:
        constraints: [node.role == manager]
    networks:
      - webnet
  redis:
    image: redis
    ports:
      - "6379:6379"
    volumes:
      - "/home/docker/data:/data"
    deploy:
      placement:
        constraints: [node.role == manager]
    command: redis-server --appendonly yes
    networks:
      - webnet
networks:
  webnet:
```
Pour manager les stacks on utilise la commande `docker stack`.  
Pour persister les données d'un container on utilise les volumes. Il est nécéssaire de connaitre la manière dont ont été buildés les images qu'on utilise pour persister les données et exposer les services.

##### Part 6 Deploy your app
**Ce qu'il faut retenir :**  
Rien de plus que ce qui est présenté en part 3/4/5. Il faut s'assurer que l'ensemble des machines est accès à un registry.   

**Cheat sheet :**  
```
docker stack deploy -c docker-compose.yml getstartedlab

Creating network getstartedlab_webnet
Creating service getstartedlab_web
Creating service getstartedlab_visualizer
Creating service getstartedlab_redis

[getstartedlab] ~ $ docker node ls
ID                            HOSTNAME                                      STATUS              AVAILABILITY        MANAGER STATUS
9442yi1zie2l34lj01frj3lsn     ip-172-31-5-208.us-west-1.compute.internal    Ready               Active              
jr02vg153pfx6jr0j66624e8a     ip-172-31-6-237.us-west-1.compute.internal    Ready               Active              
thpgwmoz3qefdvfzp7d9wzfvi     ip-172-31-18-121.us-west-1.compute.internal   Ready               Active              
n2bsny0r2b8fey6013kwnom3m *   ip-172-31-20-217.us-west-1.compute.internal   Ready               Active              Leader   

[getstartedlab] ~/sandbox/getstart $ docker service ls
ID                  NAME                       MODE                REPLICAS            IMAGE                             PORTS
x3jyx6uukog9        dockercloud-server-proxy   global              1/1                 dockercloud/server-proxy          *:2376->2376/tcp
ioipby1vcxzm        getstartedlab_redis        replicated          0/1                 redis:latest                      *:6379->6379/tcp
u5cxv7ppv5o0        getstartedlab_visualizer   replicated          0/1                 dockersamples/visualizer:stable   *:8080->8080/tcp
vy7n2piyqrtr        getstartedlab_web          replicated          5/5                 sam/getstarted:part6    *:80->80/tcp

[getstartedlab] ~/sandbox/getstart $ docker service ps vy7n2piyqrtr
ID                  NAME                  IMAGE                            NODE                                          DESIRED STATE       CURRENT STATE            ERROR               PORTS
qrcd4a9lvjel        getstartedlab_web.1   sam/getstarted:part6   ip-172-31-5-208.us-west-1.compute.internal    Running             Running 20 seconds ago                       
sknya8t4m51u        getstartedlab_web.2   sam/getstarted:part6   ip-172-31-6-237.us-west-1.compute.internal    Running             Running 17 seconds ago                       
ia730lfnrslg        getstartedlab_web.3   sam/getstarted:part6   ip-172-31-20-217.us-west-1.compute.internal   Running             Running 21 seconds ago                       
1edaa97h9u4k        getstartedlab_web.4   sam/getstarted:part6   ip-172-31-18-121.us-west-1.compute.internal   Running             Running 21 seconds ago                       
uh64ez6ahuew        getstartedlab_web.5   sam/getstarted:part6   ip-172-31-18-121.us-west-1.compute.internal   Running             Running 22 seconds ago        
```

##### Annexe sur docker-machine
Docker Machine is a tool that lets you install Docker Engine on virtual hosts, and manage the hosts with docker-machine commands. You can use Machine to create Docker hosts on your local Mac or Windows box, on your company network, in your data center, or on cloud providers like Azure, AWS, or Digital Ocean.

Using docker-machine commands, you can start, inspect, stop, and restart a managed host, upgrade the Docker client and daemon, and configure a Docker client to talk to your host.

#### Katacoda : Get Started
##### Scénario 1 Deploying Your First Docker Container
**Ce qu'il faut retenir :**  
Pour chercher une image sur un registry on utilise la commande `docker search`.  
Un simple `docker run -d nom-de-l'image` permet de "tirer" une image depuis un repository et de "démarrer" un container en mode démon.  
`docker inspect <friendly-name|container-id>` donne les détails du container.  
`docker logs <friendly-name|container-id>` donne les logs du container.  
`docker run -d --name <friendly-name> -p <host-port>:<container-port> <image>:<tag>` "tire" l'image depuis un repository "démarre" un container en mode démon via un mapping de port entre l'host et le container. On peut manager le container via le friendly-name.  
`docker run -d --name <friendly-name> -p <container-port> <image>:<tag>` "tire" l'image depuis un repository "démarre" un container en mode démon via un mapping de port dynamique. On peut manager le container via le friendly-name.  
`docker port <friendly-name> <container-port>` permet de connaitre le port dynamique utilisé.  
`docker run -d --name redisMapped -v /opt/docker/data/redis:/data redis` permet de persister les données de redis dans _/opt/docker/data/redis_.  
`docker run ubuntu ps` éxécute le container ubuntu et effectue la commande ps dans celui-ci.  
`docker run -it ubuntu bash` éxécute le container ubuntu et ouvre un shell.  

##### Scénario 2 Deploy Static HTML Website as Container
Créer une "image" pour l'instancier comme un "container" cela revient à partir d'une image éxistante et à l'enrichir.  
Pour cela on va créer un fichier _Dockerfile_ qu'on va "builder".  
Pour builder "l'image" on va utiliser la comamnde `docker build -t <friendly-name>:<tag> path_to_Dockerfile`.  
On peut voir "l'image" précédemment créé via la commande `docker images`.  
Pour instancier "l'image" en "container" on utilise la commande `docker run -d -p <host-port>:<container-port> <friendly-name>:<tag>`.  

##### Scénario 3 Building Container Images
Tout  _Dockerfile_ doit démarrer depuis la commande `FROM <image-name>:<tag>` qu'on appel une "base image".  
On peut utiliser les commandes _RUN ou COPY_ au sein de notre  _Dockerfile_.  
_RUN_ permet d'éxécuter une qqcnq commande. Par exemple on peut installer qqch ou compiler qqch.  
_COPY_ permet de copier des fichiers du repertoire où se situe le  _Dockerfile_ dans le container.  
La commande _EXPOSE_ permet de définir le/les port(s) d'exposition du container.  
La commande _CMD_ définit ce que fait le container au démarrage. On l'utilise de de la manière suivante `CMD ["nginx","-g","daemon off;"]`.  
On peut aussi utiliser la commande _ENTRYPOINT_ à la place de  _CMD_. Là où _CMD_ peux être surchargé au démarrage du container, _ENTRYPOINT_ définit une commande qui à des arguments qu'on peux passer en ligne de commande.

```docker
# This is your Editor pane. Write the Dockerfile here and
# use the command line to execute commands
# use the command line to execute commands
FROM nginx:1.11-alpine
COPY ./index.html /usr/share/nginx/html
EXPOSE 80
CMD ["nginx","-g","daemon off;"]
```

##### Scénario 4 Dockerizing Node.js
En cas de rebuild d'une image, Docker garde en cache tout ce qu'il s'est passé.  
Si une modification survient dans les fichiers contenus dans le _Dockerfile_ alors il ne rebuildera que ce qui précède la ligne du _Dockerfile_ en question.  
Cela nécessité d'orchestrer son _Dockerfile_ correctement.  
>With NPM we only want to re-run npm install if something within our package.json file has changed. If nothing has changed then we can use the cache version to speed up deployment. By using `COPY package.json <dest>` we can cause the RUN npm install command to be invalidated if the package.json file has changed. If the file has not changed, then the cache will not be invalided, and the cached results of the npm install command will be used.  

On peux s'affranchir du cache via l'option suivante de la commande build : `-no-cache=true`.  

##### Scénario 5 Optimise Builds With Docker OnBuild
La commande "ONBUILD" permet de définir des actions à éxécuter plus tard. Cette instruction est pratique dès qu'on souhaite builder une image qui sera utilisé comme "base image".
```
FROM node:7
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install
ONBUILD COPY . /usr/src/app
CMD [ "npm", "start" ]

FROM node:7-onbuild
EXPOSE 3000
```
##### Scénario 6 Ignoring Files During Build
Pour ignorer des fichiers au cours du build il suffit d'ajouter à la racine du répertoire un fichier _.dockerignore_. Ce fichier est similaire au fichier _.gitignore_.  
Au passage on peux éxécuter une commande dans le container via le passage de celle-ci après la commande run comme ceci `docker run nopassword ls /app`.  
Une bonne pratique consiste à ignorer le dossier `.git`.  

##### Scénario 7 Create Data Containers
On peux créer des container de données qu'on appel des _data containers_.  
Pour créer un _data containers_, on utilise la commande `docker create -v /config --name dataContainer busybox`.  
L'option -v permet de connaitre le répertoire "rw".  
Pour copier des donner dans le container on utilise la commande `docker cp config.conf dataContainer:/config/`.  
Pour éxécuter un autre container qui "map" le _data container_ on utilise la commande `docker run --volumes-from dataContainer ubuntu ls /config`.  
Pour exporter le _data container_ on utilise la commande `docker export dataContainer > dataContainer.tar`.  

##### Scénario 8 Creating Networks Between Containers using Links
On peut créer des liens entre les containers pour faire communiquer deux service par exemple.  
On commence par éxécuter un container cible par exemple `docker run -d --name redis-server redis`.  
Pour créer un lien on utilise la commande suivante : `docker run --link <container-cible|id>:<alias> <container-source>`.  
On peux via la commande précédante connecter une interface client à son serveur.  
Dans le cas de Redis `docker run -it --link redis-server:redis redis redis-cli -h redis`.  
Ce qui est important dans tous ça c'est de comprendre ce qu'il se passe quand docker créé un lien.  
Tout d'abbord il maj les variables d'environment de la machine source avec un certain nombre d'informations de la machine cible. Deuxiemement il met à jour le fichier /etc/hosts de la machine source avec les informations de la machine cible.  

##### Scénario 9 Creating Networks Between Containers using Networks
A la différence des liens un _docker network_ s'apparente à un "réseau virtuel" entre les containers.  
Pour créer un _docker network_ on utilise la commande `docker network create backend-network`.  
Pour attacher un container à ce _docker network_ on utilise l'option `--net <nom_du_rez>` ex : `docker run -d --name=redis --net=backend-network redis`.  
Quand on attache des containers à un _docker network_ ceux-ci vont automatiquement partager leurs informations via le DNS embarqué dans docker. On peux voir ce DNS via la commande suivante `docker run --net=backend-network alpine cat /etc/resolv.conf`.  
On peux attacher un container à un nouveau _docker network_ via la commande `docker network connect frontend-network redis`.  
On peux voir les _docker network_ via la commande `docker network ls`.  
Pour savoir quel container est rattaché à quel _docker network_ on utilise la commande `docker network inspect frontend-network`.  
On peux déconnecter les containers connecté au _docker network_ via la commande `docker network disconnect frontend-network redis`.  

##### Scénario 10 Persisting Data Using Volumes
Pour qu'un container persiste ses donner il faut les exporter dans un volume non-volatile (en dehors d'un qqcnq container).  
On utilise l'option "-v" de `docker run` pour spécifier le volume "mapper" qui va contenir les données persistées.  
Par exemple : `docker run  -v /docker/redis-data:/data --name r1 -d redis redis-server --appendonly yes`.  
On peut "pipe" les données dans le container via la commande suivant : `cat data | docker exec -i r1 redis-cli --pipe`.  
On peut aussi "mapper" le volume d'un container A avec celui d'un container via l'option `--volume-from`.  
Par ex : `docker run --volumes-from r1 -it ubuntu ls /data`.  
On peut monter un volume avec des options comme dans l'exemple suivant : `docker run -v /docker/redis-data:/data:ro -it ubuntu rm -rf /data`.  

##### Scénario 11 Manage Container Log Files
Les logs d'un container sont accessibles via la commande `docker logs <container-name|id>`.  
Au démarrage d'un container on peut choisir son "log-driver" via l'option `--log-driver=`.  
Par ex : `docker run -d --name redis-syslog --log-driver=syslog redis`.  
On peut désactiver les logs d'un container via l'option `--log-driver=none`.  
Par ex : `docker run -d --name redis-none --log-driver=none redis`.  
Pour connaitre la configuration des logs on utilise la comamnde suivante : `docker inspect --format '{{ .HostConfig.LogConfig }}' redis-server`.  

##### Scénario 12 Ensuring Container Uptime With Restart Policies
Un container peut comme n'importe quel process "planter". Docker via l'option `--restart` spécifer le nombre de redémarrage avant un véritable crash.  
Par exemple pour redémarrer 3 fois le container on utilise la commande : `docker run -d --name restart-3 --restart=on-failure:3 scrapbook/docker-restart-example`.  
Pour redémarrer le container quoi qu'il arrive on utilisera la commande suivante : `docker run -d --name restart-always --restart=always scrapbook/docker-restart-example`.  

##### Scénario 13 Adding Docker Metadata & Labels
On peut ajouter un certain nombre de metadata dans des containers ou des images.  
Les metadata sont gérées via ce qu'on appel des labels.  
Pour ajouter un label au démarrage d'un container on utilise l'option `-l=<value>` de la commande `docker run`. Par exemple : `docker run -l user=12345 -d redis`.  
On peut ajouter un fichier entier contenant des lables via  `docker run --label-file=labels -d redis`.  
On peut créer des labels dans une image directement via le _Dockerfile_ via la commande `LABEL`.  
```
LABEL vendor=Katacoda
LABEL vendor=Katacoda \ com.katacoda.version=0.0.5 \ com.katacoda.build-date=2016-07-01T10:47:29Z \ com.katacoda.course=Docker
```
Pour connaitre les labels d'une image ou d'un container on utilise la commande `docker inspect rd`.  
On peut alors "filtrer" les containers ou les images sur des labels via l'option `--filter`. Par exemple `docker ps --filter "label=user=scrapbook"` ou encore `docker images --filter "label=vendor=Katacoda"`.  
Pour ajouter des labels directement dans le démon unix :
```
docker -d \
-H unix:///var/run/docker.sock \
--label com.katacoda.environment="production" \
--label com.katacoda.storage="ssd"
```
##### Scénario 14 Load Balancing Containers
Ce scénario utilise un container spécifique "nginx_proxy" pour proxyfier et load-balancer des containers web. Le seul intérêt de ce tuto est qu'il aborde la notion de "Service Discovery" via les "Docker's API.".  

##### Scénario 15 Orchestration using Docker Compose
Docker Compose permet d'orchestrer des applications mutli-containers.  
Docker Compose est basé sur un fichier yaml _docker-compose.yml_ qui à la forme suivante.  
```yaml
container_name:
  property: value
    - or options
```
Pour démarrer l'application on utilise la commande `docker-compose up -d`.  
Pour voir les containers démarré on utilise la commande `docker-compose ps`.  
Pour accéder au log `docker-compose log`.  
Pour scaler un service précis on utilise la commande suivante : `docker-compose scale web=3`.  
Pour arréter une application on utilisera `docker-compose stop`.  
Pour supprimer tous les containers `docker-compose rm`.  
Attention docker-compose n'est pas la meme chose que docker stack (voir le lien suivant https://nickjanetakis.com/blog/docker-tip-23-docker-compose-vs-docker-stack )

##### Scénario 16 See Container Metrics With Docker Stats
Pour connaitre les métrics d'un container on utilise la commande `docker stats nginx`.  
Pour connaitre les métrics de plusieurs containers on utilise la commande `docker ps -q | xargs docker stats`.  


##### Scénario 17 Creating Optimised Docker Images using Multi-Stage Builds
>The Multi-Stage feature allows a single Dockerfile to contain multiple stages in order to produce the desired, optimised, Docker Image.  
Previously, the problem would have been solved with two Dockerfiles. One file would have the steps to build the binary and artifacts using a development container, the second would be optimised for production and not include the development tools.  
By removing development tooling in the production image, you reproduce the attack surface and improve the deployment time.  

Un exemple de fichier Multi-Stage.
```Dockerfile
# First Stage
FROM golang:1.6-alpine

RUN mkdir /app
ADD . /app/
WORKDIR /app
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main .

# Second Stage
FROM alpine
EXPOSE 80
CMD ["/app"]

# Copy from first stage
COPY --from=0 /app/main /app
```
Pour Builder l'image on utilise la commande suivant `docker build -f Dockerfile.multi -t golang-app .`

##### Scénario 18 Formatting PS Output
On peux formatter la sortie de `docker ps` via l'option ` --format`.  
`docker ps --format '{{.Names}} container is using {{.Image}} image'`.  
`docker ps --format 'table {{.Names}}\t{{.Image}}'`.  
`docker ps -q | xargs docker inspect --format '{{ .Id }} - {{ .Name }} - {{ .NetworkSettings.IPAddress }}'`.  

##### Scénario 19 Learn Docker Swarm
On peux "clusteriser" docker avec le mode _Swarm_.  
On démarre un cluster _Swarm_ avec la commande `docker swarm init`.  
Le premier cluster devient un cluster "manager" il renseigne un token qu'il faut garder dans un endroit sécurisé. Ce token permet aux autres "node" de s'enregistrer au cluster.  
Depuis un "node" externe au cluster, on peut utiliser la commande suivante pour récupérer le token :
`token=$(docker -H 172.17.0.33:2345 swarm join-token -q worker) && echo $token`.  
on rejoit alors le cluster avec la commande suivante :
`docker swarm join 172.17.0.33:2377 --token $token`.  
Pour connaitre la liste des "nodes" qui composent le cluster on utilise la commande `docker node ls` depuis le "master".

Le mode _Swarm_ déploie un model de réseau nouveau et plus robuste, permettant le dialogue et la scalabilité entre chaque "node" du cluste.  
Pour créer un reseau "overlay" dans le cluster swarm on utilise la commande : `docker network create -d overlay skynet` depuis le "master".  

Le mode _Swarm_ ajoute la notion de "service" qui est "au dessus" du container. Celle-ci permet de défnir un ou plusieurs container composant un "service" avec des règles de deploiement de réplication de scalabilité ...  
Dans cet exemple on va créer un service qui contient deux serveur http. Ceux-ci sont automatiquement répliqué et load balancé sur l'ensemble du cluster swarm. `docker service create --name http --network skynet --replicas 2 -p 80:80 katacoda/docker-http-server`.  
Pour connaitre les services en cours on utilise la commande `docker service ls` depuis le "master".  
Pour connaitre l'état d'un service en particulier `docker service ps <service_name>`.  
Pour inspecter un service en particulier `docker service inspect --pretty <service_name>`.  
Pour connaitre les containers du "node" `docker node ps self`.  
Depuis le master pour connaitre les containers d'un "node" `docker node ps $(docker node ls -q | head -n1)`.  
Pour scaler le nombre d'instance d'un service en cli : `docker service scale <service_name>=<nombre_d'instance>` ex : `docker service scale http=5`


### Source
[Get Docker](https://docs.docker.com/install/)  
[Get Docker CE for CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)  
[Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/)  
[Get Started](https://docs.docker.com/get-started/)  
[Docker Machine](https://docs.docker.com/machine/overview/)
[Katacoda Docker](https://www.katacoda.com/courses/docker)
