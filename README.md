# Prototyping server setup

These convenient hackathon tools can be deployed under any domain (see .env files).

## Setup

Read the compose and configuration files while looking for `TODO` markers.
There are some values like passwords and domain data that you need to fill in yourself.
Once that is done (and you have docker compose of course) you can start.

> Hint: You can run the entire thing locally by having "localhost" as your domain name.
> Helps with debugging.

## Starting the services

```shell
cd routing
docker compose up -d

cd ../prototyping
docker compose up -d
```

If you want to see what's going on in the services defined in the respective compose files,
navigate to their home folder and run `docker compose logs -f`.

This especially makes sense if you want to see how far Baserow is (it takes a while on the initial setup).

## How to use

Traefik is separate from the other tools to allow adding and removing services without taking the rest down with them.
The only downside is, you need to start it before the rest. You'll probably do this exactly once.
After that, you can add different services (f.e. penpot for designs, some cloud file storage, etc.) without affecting the rest.
There's also the ´panel.<domain_name>` page where you can see all running services.