# 🐀 Ratiscrum Api

## Project informations

Nuit de l'info 2022 !

## 💻 Developpers guide

### Requirements
- Docker et Docker Compose

### Installation

#### Prod

- Créer un réseau Docker nommé `web` (`docker network create web`)
- Créer un reverse proxy (`traefik` de préférence) rattaché au réseau `web`
- Faire une copie du fichier `.env.example` et l'appeler ` .env`
- Remplir les champs avec les valeurs voulues
- Lancer le tout avec la commande `docker-compose --env-file .env up -d`  

#### Développement 

Avec Docker, entrez les commandes suivantes 
```sh
# Lancement d'une base de données postgis
docker run -d --name rts-bdd -e POSTGRES_DB="<un nom de bdd de votre choix>" -e POSTGRES_USER="<un nom d'utilisateur de votre choix>" -e POSTGRES_PASSWORD="<un mot de passe de votre choix>" -p 5432:5432 postgis/postgis

# Lancement d'un S3 Minio
docker run -d --name rts-minio -e MINIO_ROOT_USER="<un nom d'utilisateur de votre choix>" -e MINIO_ROOT_PASSWORD="<un mot de passe de votre choix>" -p 9000:9000 -p 9001:9001 minio/minio server /data --console-address ":9001"
```

