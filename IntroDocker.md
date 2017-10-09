# Docker

Docker es un software para la creacion y manejo de contenedores que ha construido un ecosistema de **imagenes** 
(basadas en registros e indices) que permiten estadarizar la forma de desplegar contenedores en las plataformas que
los soportan (Linux/Windows/Mac OSX).

![cool cat](images/catkeyboard%402x-min.png)

## Instalacion

```
$ sudo dnf install docker
```
## docker hub 

Podemos revisar [el docker hub.](https://hub.docker.com/explore/)

## Primer docker run

```
$ sudo docker hello-world
$ sudo docker run -i -t alpine echo 'Hola mundo'
```
## Listar imagenes
```
$ sudo docker images
```

## Listar contendores 

```
$ sudo docker ps -a
```
## Traer imagenes
**sudo docker pull Nombre**
```
$ sudo docker pull nginx
```
## Contendores Nombrados
```
sudo docker run --name hamster alpine echo 'Desde hamster'
```
## Exponer puertos
```
sudo docker run --name docker-nginx -p 80:80 nginx
```
## Modo background
```
sudo docker run --name docker-nginx -d nginx
```
## Detener contendor
```
sudo docker stop docker-nginx
```
## Borrar contenedor
```
sudo docker rm docker-nginx 
```
## Ligar directorio local y contendor
```
mkdir html
$ sudo docker run -name docker-nginx -p 80:80 -d -v ./html:/usr/share/nginx/html nginx
```
