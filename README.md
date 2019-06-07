# Traefik - HTTPS

A very very quick setup of [Traefik](https://github.com/containous/traefik/) as a reverse proxy.

![img](https://raw.githubusercontent.com/containous/traefik/master/docs/content/assets/img/traefik-architecture.png)

This setup also configures a simple [GO API](https://hub.docker.com/r/jeskz0rd/docker-bootcamp) that runs on port `8000` and is only available to be accessed through Traefik.

At the moment, this setup should be used for test purposes only.

I developed this solution to be used as a reverse proxy guide. There's a lot of work to be done here, so feel free to develop by your own, open a PR or an issue :)

> NOT RECOMMENDED FOR PRODUCTION
>
> NOT SUITABLE FOR PRODUCTION

## TL;DR

### Proxy network setup

`docker network create proxy --attachable`

### Traefik proxy setup

`docker-compose -f traefik.yml up -d`

### Sample application

`docker-compose -f app.yml up -d`

### Connectivity test

`curl -i -H "Host: jeskz0rd.example" http://127.0.0.1`

`curl -i -H "Host: jeskz0rd.example" --insecure https://127.0.0.1`

`curl -i -H "Host: www.jeskz0rd.example" http://127.0.0.1`

`curl -i -H "Host: www.jeskz0rd.example" --insecure https://127.0.0.1`

### Finish test

`docker-compose -f traefik.yml down`

`docker-compose -f app.yml down`

`docker network rm proxy`
