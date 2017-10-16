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
**Solo** puede existir 
