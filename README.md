# LemonLDAP playground

This playground aim to play with LemonLDAP.

## Requirements

- [docker](https://www.docker.com/)

## Getting started

For now this repository only contain a docker-service that serve a hello-world
web page that is protected by a LemonLDAP instance. Configuration can be found
in [config](./config/) folder.

First you should edit your hosts to get local domain configuration:

```
echo "127.0.0.1 auth.example.com manager.example.com reload.example.com docker.example.com" | sudo tee -a /etc/hosts
```

Then you should launch the containers:

```
$ docker compose up -d
[+] Running 3/3
 ✔ Network lemomldap-playground_default             Created
 ✔ Container lemomldap-playground-lemonldap-1       Started
 ✔ Container lemomldap-playground-docker-service-1  Started
```

You should now be able to go on `http://docker.example.com` and login with
default credentials `dwho/dwho`.

## Stop

If you want to stop the containers, use:

```
$ docker compose down
[+] Running 3/3
 ✔ Container lemomldap-playground-lemonldap-1       Removed
 ✔ Container lemomldap-playground-docker-service-1  Removed
 ✔ Network lemomldap-playground_default             Removed
```
