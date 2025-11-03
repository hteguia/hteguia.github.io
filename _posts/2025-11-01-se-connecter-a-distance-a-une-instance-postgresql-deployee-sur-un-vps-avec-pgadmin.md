---
title: "Se connecter à distance à une instance PostgreSQL déployée sur un VPS avec PgAdmin"
description: "Ce mini-guide pratique décrit comment établir une connexion à une base de données PostgreSQL hébergée dans un conteneur Docker sur un serveur distant, en passant par une connexion SSH. Cette approche est particulièrement utile pour les environnements de laboratoire."
date: 2025-11-01
categories: [PostgreSQL, Docker]
tags: [PostgreSQL, Docker, PgAdmin, VPS, Remote Access]
---

Dans ce guide pratique, nous allons :

- Déployer PostgreSQL sur un VPS avec Docker.
- Se connecter depuis PgAdmin sur une machine locale a travers une connexion SSH.

Prérequis

- Un serveur distant (VPS ou machine Linux) accessible via SSH
- Docker installé et en cours d’exécution sur ce serveur
- Un compte utilisateur SSH sur le serveur
- L’adresse IP ou le nom de domaine du serveur distant
- Sur ta machine locale :
    PgAdmin


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

Vérifiez que le conteneur a démarré correctement.

```bash
$ docker ps
```

A partir du _container_id_, afficher toutes les informations détaillées du conteneur sous forme de JSON

```bash
$ docker inspect <container_id>
```

Cette commande permet de recupérer rapidement l’adresse IP interne du conteneur

NB : 
- Cette IP est interne au réseau Docker du serveur, elle n’est pas accessible directement depuis l’extérieur.
Pour y accéder depuis ta machine locale, il faudra passer par un tunnel SSH
- Si PostgreSQL avait été installé directement sur notre VPS, nous aurions utilisé l’adresse 127.0.0.1, qui correspond à l’adresse interne du serveur. 

Une fois la configuration du VPS terminée, passons à la configuration de la connexion depuis notre machine locale.

## 2. Se connecter depuis PgAdmin sur une machine locale a travers une connexion SSH

2.1. Information générale

- (1) Nom que vous souhaitez attribuer à votre serveur dans l’explorateur de PgAdmin

![Texte alternatif](/assets/images/2025-11-01-se-connecter-a-distance-a-une-instance-postgresql-deployee-sur-un-vps-avec-pgadmin/connexion-name.png )

2.2. Informations de connexion à la base de données PostgreSQL

- (1) Adresse IP interne de votre instance Docker
- (2) Port interne sur lequel votre base de données PostgreSQL est déployée
- (3) Nom de la base de données à laquelle se connecter
- (4) Nom d’utilisateur de la base de données
- (5) Mot de passe associé à cet utilisateur

![Texte alternatif](/assets/images/2025-11-01-se-connecter-a-distance-a-une-instance-postgresql-deployee-sur-un-vps-avec-pgadmin/db-connexion.png )

2.3. Informations de connexion SSH à votre VPS

- (2) Adresse IP publique de votre VPS
- (3) Port SSH par défaut
- (4) Nom de l’utilisateur SSH
- (5) Type de connexion : mot de passe
- (6) Mot de passe de l’utilisateur SSH

![Texte alternatif](/assets/images/2025-11-01-se-connecter-a-distance-a-une-instance-postgresql-deployee-sur-un-vps-avec-pgadmin/ssh-tunnel-password.png )

Vous poucvez utiliser cette approche si vous avez deja configurer la connexion ssh a votre serveur sans mot de passe. 

![Texte alternatif](/assets/images/2025-11-01-se-connecter-a-distance-a-une-instance-postgresql-deployee-sur-un-vps-avec-pgadmin/ssh-tunnel.png )
