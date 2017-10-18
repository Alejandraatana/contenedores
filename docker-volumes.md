# Volumenes

Los volumenes son la forma recomendada de mantener persistencia de la informacion en contendores de docker. Aunque existen los puntos de montaje (asocian el contenido de un directorio de host a un dentro del contenodor) estos ultimos no son portables e implican riesgos de seguridad si no son bien configurados.

Algunas ventajas de los volumenes son:
* Faciles de respaldar y compartir.
* Se pueden generar desde la linea de comandos.
* Caracteristica portable entre plataformas.
* Pueden ser compartidos entre multilples contenedores.
* Soportan cifrado y acceso local y/o remoto.
* Puede ser llenado por medio de un contendor.

## Crear Volumenes
```
$ sudo docker volume create mis-cachetes
```
## listar Volumenes
```
$ sudo docker volume ls
```
## Inspeccionar Volumenes
```
$ sudo docker volume inspect mis-cachetes
```
## Borrar Volumenes
```
$ sudo docker volume rm mis-cachetes
```

## Volume Sintaxis

```
$ sudo docker run --name torta-de-jamon -p 80:80 -d -v mis-cachetes:/usr/share/nginx/html nginx
$ sudo docker inspect torta-de-jamon
$ sudo docker stop torta-de-jamon
$ sudo docker run -v mis-cachetes:/app busybox ls /app
```
## Uniendo todo :octocat:

```
$ docker run --name mi-mysql -v mis-2-cachetes:/var/lib/mysql -p 3306:3306 -e MYSQL_ROOT_PASSWORD=Hamster -d mysql
```



