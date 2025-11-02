---
title: "Se connecter à distance à une instance PostgreSQL déployée sur un VPS avec PgAdmin"
description: "Ce mini-guide pratique décrit comment établir une connexion à une base de données PostgreSQL hébergée dans un conteneur Docker sur un serveur distant, en passant par une connexion SSH. Cette approche est particulièrement utile pour les environnements de laboratoire."
date: 2025-11-01
categories: [PostgreSQL, Docker]
tags: [PostgreSQL, Docker, PgAdmin, VPS, Remote Access]
---

## Introduction

Dans ce guide pratique, nous allons :

- Déployer PostgreSQL sur un VPS avec Docker.
- Configurer PostgreSQL pour accepter les connexions distantes.
- Se connecter depuis PgAdmin sur une machine locale.
- Mettre en place des mesures de sécurité pour protéger votre base de données.

## 1. Déployer PostgreSQL sur le VPS avec Docker

Exécutez la commande suivante sur votre VPS :

```bash
docker run -d \
  --name pg-docker \
  -e POSTGRES_USER=monuser \
  -e POSTGRES_PASSWORD=monmotdepasse \
  -e POSTGRES_DB=madatabase \
  -p 5432:5432 \
  -v pgdata:/var/lib/postgresql/data \
  postgres:16
  ```

  ```bash
$ docker ps
CONTAINER ID   IMAGE
def012345678   postgres:15-alpine
```

```bash
$ docker inspect def012345678 | grep IPAddress
  "SecondaryIPAddresses": null,
  "IPAddress": "",
    "IPAddress": "666.13.0.1",
```

![Texte alternatif](/assets/images/2025-11-01-se-connecter-a-distance-a-une-instance-postgresql-deployee-sur-un-vps-avec-pgadmin/1.png )
