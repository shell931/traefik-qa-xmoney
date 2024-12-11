# TRAEFIK QA XMONEY  

Service to __SERVICE_SUMMARY__.

## SETUP
```bash

traefik/
└── dist/
    └── app-angular
└── docker-compose.yml
└── letsencrypt/
    └── acme.json  # chmod 600 acme.json
└── nginx/
    └── nginx.conf
└── static-files/
    └── .well-known


echo "{}" > /home/traefik/letsencrypt/acme.json
chmod 600 /home/traefik/letsencrypt/acme.json

```

### INSTALL

```bash
# linux
docker-compose up --build
```

### DELETE AND CLEAN DOCKER

```bash
# linux
# Detener todos los contenedores en ejecución
echo "Deteniendo todos los contenedores..."
docker stop $(docker ps -aq)

# Eliminar todos los contenedores
echo "Eliminando todos los contenedores..."
docker rm $(docker ps -aq)

# Eliminar todas las imágenes
echo "Eliminando todas las imágenes..."
docker rmi $(docker images -q)

# Eliminar todos los volúmenes
echo "Eliminando todos los volúmenes..."
docker volume prune -f

# Eliminar todas las redes no utilizadas
echo "Eliminando redes no utilizadas..."
docker network prune -f

# Eliminar la caché de construcción
echo "Eliminando la caché de construcción..."
docker builder prune -af

echo "Limpieza completa. Todo el sistema Docker ha sido reseteado."
```

### DOCKERFILE
There are two dockerfiles.
Dockerfile.dev is used by docker-compose.yml and is used to develop because it allows hot reload
Dockerfile will be used in dev, stage and prod environments


# ACKNOWLEDGMENTS

* Powered by [Carlos Arriero](mailto:desarrollo@dyner24.com) 😎
