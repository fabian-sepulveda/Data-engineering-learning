Este video fue una introducción a Docker.

En si no se vieron cosas complejar, se armo un "Dockerfile" simple.

# Dockerfile
FROM -> versión de la imagen que se trabajará.
RUN -> se emplea para ejecutar lineas de comando al momento de levantar el entorno.

    * Tratar siempre de marcar las librerías que se van a usar para no dar problemas al ejecutar.

WORKDIR -> indica el directorio de ejecución dentro del contenedor.
COPY -> copia el archivo indicado, se le debe dar una etiqueta posterior al nombre del archivo original.
ENTRYPOINT -> lo que ejecutara el contenedor al iniciarse la ejecución.



# Ejecutar Dockerfile

BUILD : Se emplea para crear la imagen del contenedor

    -> docker build -t <Nombre del contenedor>

RUN : Se emplea para ejecutar el contenedor

    -> docker run -it <Nombre del contenedor>


