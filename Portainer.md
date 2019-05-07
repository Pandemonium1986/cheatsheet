# Portainer : Installation et Configuration

## Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
| Portainer |  1.20.2 |
|   Docker  | 18.09.5 |

## Todo

N/A

## Note en vrac

N/A

## Avant propos

> Portainer is a simple management solution for Docker.
> It consists of a web UI that allows you to easily manage your Docker containers, images, networks and volumes.

## Procédure d'installation docker

**Quick start**  

```sh
docker volume create portainer_data
docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

**Advanced deployment**  

Deploy Portainer via docker-compose :  

```yaml
version: '2'

services:
  portainer:
    image: portainer/portainer
    command: -H unix:///var/run/docker.sock
    restart: always
    ports:
      - 9000:9000
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data

volumes:
  portainer_data:
```

Declaring the Docker environment to manage upon deployment :  

```sh
docker run -d -p 9000:9000 --name portainer --restart always -v portainer_data:/data portainer/portainer -H tcp://<REMOTE_HOST>:<REMOTE_PORT>
docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer -H unix:///var/run/docker.sock
```

Secure Portainer using SSL :  

```sh
docker run -d -p 443:9000 --name portainer --restart always -v ~/local-certs:/certs -v portainer_data:/data portainer/portainer --ssl --sslcert /certs/portainer.crt --sslkey /certs/portainer.key
```

### Procédure de post-installation

**Configuration Admin password**

```sh
htpasswd -nb -B admin <password> | cut -d ":" -f 2
docker run --rm httpd:2.4-alpine htpasswd -nbB admin <password> | cut -d ":" -f 2

docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock portainer/portainer --admin-password='$2y$05$qFHAlNAH0A.6oCDe1/4W.ueCWC/iTfBMXIHBI97QYfMWlMCJ7N.a6'
```

**Available flags**   

-   **--admin-password:** Admin password in the form admin:&lt;hashed_password>
-   **--admin-password-file:** Path to the file containing the password for the admin user
-   **--bind, -p:** Address and port to serve Portainer (default: :9000)
-   **--data, -d:** Directory where Portainer data will be stored (default: /data on Linux, C:\\data on Windows)
-   **--external-endpoints:** Enable external endpoint management by specifying the path to a JSON endpoint source in a file
-   **--hide-label, -l:** Hide containers with a specific label in the UI
-   **--host, -H:** Docker daemon endpoint
-   **--logo:** URL to a picture to be displayed as a logo in the UI, use Portainer logo if not specified
-   **--no-analytics:** Disable analytics (default: false)
-   **--no-auth:** Disable internal authentication mechanism (default: false)
-   **--no-snapshot:** Disable periodic endpoint snapshot (default: false)
-   **--snapshot-interval:** Time interval between two endpoint snapshot jobs expressed as a string, e.g. 30s, 5m, 1h… as supported by the time.ParseDuration method (default: 5m)
-   **--ssl:** Secure Portainer instance using SSL (default: false)
-   **--sslcert:** Path to the SSL certificate used to secure the Portainer instance (default: /certs/portainer.crt, C:\\certs\\portainer.crt on Windows)
-   **--sslkey:** Path to the SSL key used to secure the Portainer instance (default: /certs/portainer.key, C:\\certs\\portainer.key on Windows)
-   **--sync-interval:** Time interval between two endpoint synchronization requests expressed as a string, e.g. 30s, 5m, 1h… as supported by the time.ParseDuration method (default:\*\* 60s)
-   **--templates, -t:** URL to templates (apps) definitions
-   **--template-file:** Path on disk to templates (apps) definitions (default: /templates.json)
-   **--tlscacert:** Path to the CA (default: /certs/ca.pem on Linux, C:\\certs\\ca.pem on Windows)
-   **--tlscert:** Path to the TLS certificate file (default: /certs/cert.pem, C:\\certs\\cert.pem on Windows)
-   **--tlskey:** Path to the TLS key (default: /certs/key.pem, C:\\certs\\key.pem on Windows)
-   **--tlsverify:** TLS support (default: false)

## Source

[Portainer](https://www.portainer.io/)  
[Portainer Documentation](https://portainer.readthedocs.io/en/stable/)  
[Portainer Docker](https://hub.docker.com/r/portainer/portainer)  
[Portainer Swagger](https://app.swaggerhub.com/apis/deviantony/Portainer/1.20.2/)  
