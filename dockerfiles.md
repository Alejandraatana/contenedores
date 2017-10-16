# Dockerfile

Es un archivo de texto que contiene las intrucciones que permiten ensamblar y contruir una imagen.

## Uso
* Contextual
```bash
$ docker build .
```
* Especificando archivo
```bash
$ docker build -f /path/to/a/Dockerfile .
```
* Agregando etiquetas
```
$ docker build -t hamster/myapp .
```

## Formato
El formato de un archivo `Dockerfile` se peude resumir como:

```
# Comentario
COMANDO argumentos
```
## Comando FROM
```
FROM image [as Alias]
FROM image:tag [as Alias]
```
## Comando RUN
Tiene dos formas:
* Shell 
```
RUN /bin/bash -c 'echo Hamster' 
```
* Exec
```
RUN ["/bin/bash","-c","echo Hamster"]
```
## Comando CMD
El objetivo de `CMD` es proveer la aplicacion de arranque del contenedor. __Solo__ puede existir un comando `CMD` 

* Shell 
```
CMD /bin/bash -c 'echo Hamster' 
```
* Exec
```
CMD ["/bin/bash","-c","echo Hamster"]
```
* Entrypoint (Requiere el comando ENTRYPOINT)
```
CMD ["-c","echo Hamster"]
```
## Comando LABEL

Permite generar valores, variables dentro del `Dockerfile`

```
LABEL MAINTAINER="Srita. Hamster Cacheton"
LABEL version="1.0"
```

## Comando EXPOSE
El comando Expose le informa a docker que el contendor escucha/sirve en un determinado puerto y protocolo de red
```
EXPOSE PuertoExterno:PuertoInterno/Protocolo 
```
## Comando ENV
Genera variables de entorno dentro del contenedor

```
ENV HOSTNAME "Hamster" 
```

## Comando ADD y COPY

* ADD copia el contenido de una URL fuente (local o remota) al destino dentro del contendor, ademas soporta descompresion.
```
ADD <fuente>... <destino>
ADD ["<fuente>",... "<destino>"]
```
* COPY copia el contenido de una fuente __local__ al destino dentro del contendor.
```
COPY <fuente>... <destino>
COPY ["<fuente>",... "<destino>"]
```
## ENTRYPOINT
Configura el contenedor con una aplicacion para ejecutar un problema.
```
ENTRYPOINT ["ejecutable", "param1", "param2"]
ENTRYPOINT comando param1 param2
```
En conjunto con `CMD` 
```
FROM busybox
ENTRYPOINT ["/bin/bash", "-c"]
CMD ["echo Hamster"]
```
## Comando WORKDIR
Establece el directorio de trabajo para el resto de los comandos
```
WORKDIR /home/hamster
```

## Comando VOLUME
Define un punto de montaje para un volumen de docker

```
VOLUME ["/data"]
VOLUME /data
```
