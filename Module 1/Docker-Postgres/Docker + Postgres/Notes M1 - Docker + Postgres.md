# Docker Compose

Nos permite crear todo el entorno

comando util : docker compose up

Luego tuve un error con los "volumes"

Por alguna razón la conexión no se me realizaba correctamente, así que agregue "volumes" dejando abierta, para que se creara la base de datos con el compose up

# PGCLI

Nos sirve para estudiar la base de datos a través de consola.

Para instalarla: pip install pgcli

Luego debes entrar con: pgcli -h localhost -p 5432 -U airflow -d ny_taxi (SEGUN LO QUE SE HAYA CREADO CON EL DOCKER COMPOSE)

# Archivo Upload-data

Vimos un acercamiento al consumo de datos a través de batch.

En particular tuve que descargar el archivo desde otra página, ya que no esta el CSV disponible.

# Conocimientos adquiridos

* El uso de docker compose en el entorno
* Conexión a postgres (Hay que estar muy atento a las credenciales agregadas ya que pueden ser un dolor de cabeza si se configuran mal)
