# Introduccion video

En la primera parte se analisa un poco la base de datos, con lo que se ha cargado previamente. (Como el dataset actual no estaba en formato .csv, descargue uno con menores datos y en csv, para poder trabajarlo más rápido, esto ya del video anterior para aclararlo).

El objetivo entonces es poder usar PGadmin, una herramiente para postgres. Para reemplazar el PGcli. Pero emplearemos docker para esto.

**Comando**

docker run -it `
  -e PGADMIN_DEFAULT_EMAIL="admin@admin.com" `
  -e PGADMIN_DEFAULT_PASSWORD="root" `
  -p 8080:80 `
  dpage/pgadmin4:snapshot



# PGADMIN

- Se debe entrar a la dirección localhost:8080.
- Entrar con las credenciales ingresadas en el primer comando.

## Conexión con Postgres

PROBLEMA: Postgres se encuentra en otro contenedor.

SOLUCION: Levantar los dos contenedores sobre el mismo entorno. DOCKER network

**Comando**

docker network create pg-network

Esto entrega una ID que se debe considerar. 53774f95cc5e27b2520630d6567bac49ed2e43c544974807272090cd2bed1c74

### Contenedor Postgres

docker run -it `
  -e POSTGRES_USER="root" `
  -e POSTGRES_PASSWORD="root" `
  -e POSTGRES_DB="ny_taxi" `
  -v ${PWD}\ny_taxi_postgres_data:/var/lib/postgresql/data `
  -p 5431:5432 `
  --network=pg-network `
  --name pg-database `
  postgres:13

### Contenedor PGadmin

docker run -it `
  -e PGADMIN_DEFAULT_EMAIL="admin@admin.com" `
  -e PGADMIN_DEFAULT_PASSWORD="root" `
  -p 8080:80 `
  --network=pg-network `
  --name pgAdmin `
  dpage/pgadmin4:snapshot


# Resumen de la sección

- Se introduce una nueva tecnología, que facilita la visualzación como pgAdmin, ya lo había trabajado pero desde localhost fue nuevo en mi caso.

- También encuentro importante la introducción de lo que seria el docker network, para comunicar dos contenedores y así poder crear redes. 