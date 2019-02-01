# Docker Compose : Installation et Configuration

### Version des outils

| Os / Tool |  Version |
| :-------: | :------: |
|   CentOs  | 7.4.1708 |
| Docker Ce |  18.09.0 |

### Note en vrac

#### Overview of Docker Compose

Compose is a tool for defining and running multi-container Docker applications. With Compose, you use a YAML file to configure your application’s services. Then, with a single command, you create and start all the services from your configuration. To learn more about all the features of Compose,

Compose has commands for managing the whole lifecycle of your application:

    Start, stop, and rebuild services
    View the status of running services
    Stream the log output of running services
    Run a one-off command on a service

The features of Compose that make it effective are:

    Multiple isolated environments on a single host
    Preserve volume data when containers are created
    Only recreate containers that have changed
    Variables and moving a composition between environments


Compose has traditionally been focused on development and testing workflows


#### Install Docker Compose
```sh
sudo curl -L "https://github.com/docker/compose/releases/download/1.23.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose

# I needed
sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```


### Source

[Get Docker](https://docs.docker.com/install/)  
[Get Docker CE for CentOS](https://docs.docker.com/install/linux/docker-ce/centos/)  
[Post-installation steps for Linux](https://docs.docker.com/install/linux/linux-postinstall/)  
[Get Started](https://docs.docker.com/get-started/)  
[Docker Machine](https://docs.docker.com/machine/overview/)
[Katacoda Docker](https://www.katacoda.com/courses/docker)
