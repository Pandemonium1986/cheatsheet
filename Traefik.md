# Traefik : Installation et Configuration

## Version des outils

| Os / Tool | Version |
| :-------: | :-----: |
|   Gitlab  |  1.7.X  |
|   Docker  | 18.09.6 |

## Todo

N/A

## Note en vrac

## Avant propos

> Traefik is a modern HTTP reverse proxy and load balancer that makes deploying microservices easy. Traefik integrates with your existing infrastructure components (Docker, Swarm mode, Kubernetes, Marathon, Consul, Etcd, Rancher, Amazon ECS, ...) and configures itself automatically and dynamically. Pointing Traefik at your orchestrator should be the only configuration step you need.  .

## Getting Started

Exécuter simplement le docker-compose suivant :  

```yaml
version: '3'

services:
  reverse-proxy:
    image: traefik # The official Traefik docker image
    command: --api --docker # Enables the web UI and tells Traefik to listen to docker
    ports:
      - "80:80"     # The HTTP port
      - "8080:8080" # The Web UI (enabled by --api)
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock # So that Traefik can listen to the Docker events
  whoami:
    image: containous/whoami # A container that exposes an API to show its IP address
    labels:
      - "traefik.frontend.rule=Host:whoami.docker.localhost"
```

Testons avec curl :

```sh
curl -H Host:whoami.docker.localhost http://127.0.0.1
```

En scalant :

```sh
docker-compose scale whoami=2
curl -H Host:whoami.docker.localhost http://127.0.0.1
```

### Features

-   Continuously updates its configuration (No restarts!)
-   Supports multiple load balancing algorithms
-   Provides HTTPS to your microservices by leveraging Let's Encrypt (wildcard certificates support)
-   Circuit breakers, retry
-   High Availability with cluster mode (beta)
-   See the magic through its clean web UI
-   Websocket, HTTP/2, GRPC ready
-   Provides metrics (Rest, Prometheus, Datadog, Statsd, InfluxDB)
-   Keeps access logs (JSON, CLF)
-   Fast
-   Exposes a Rest API
-   Packaged as a single binary file (made with ❤️ with go) and available as a tiny official docker image

### Supported Providers

-   Docker / Swarm mode
-   Kubernetes
-   Mesos / Marathon
-   Rancher (API, Metadata)
-   Azure Service Fabric
-   Consul Catalog
-   Consul / Etcd / Zookeeper / BoltDB
-   Eureka
-   Amazon ECS
-   Amazon DynamoDB
-   File
-   Rest

### Concepts

Quick overview  
![Overview](/img/tfk-001.png)

Zoom into traefik  
![Zoom](/img/tfk-002.png)

-   Incoming requests end on entrypoints, as the name suggests, they are the network entry points into Traefik (listening port, SSL, traffic redirection...).
-   Traffic is then forwarded to a matching frontend. A frontend defines routes from entrypoints to backends. Routes are created using requests fields (Host, Path, Headers...) and can match or not a request.
-   The frontend will then send the request to a backend. A backend can be composed by one or more servers, and by a load-balancing strategy.
-   Finally, the server will forward the request to the corresponding microservice in the private network.

#### Entrypoints

Entrypoints are the network entry points into Traefik. They can be defined using:

-   a port (80, 443...)
-   SSL (Certificates, Keys, authentication with a client certificate signed by a trusted CA...)
-   redirection to another entrypoint (redirect HTTP to HTTPS)

#### Frontends

A frontend consists of a set of rules that determine how incoming requests are forwarded from an entrypoint to a backend.

#### Backends

A backend is responsible to load-balance the traffic coming from one or more frontends to a set of http servers.

#### Configuration

Traefik's configuration has two parts:

-   The static Traefik configuration which is loaded only at the beginning.
-   The dynamic Traefik configuration which can be hot-reloaded (no need to restart the process).

## Source

[Traefik](https://traefik.io/)  
[Traefik Documentation](https://docs.traefik.io/v2.0/)  
[Traefik Docker](https://hub.docker.com/_/traefik)  
