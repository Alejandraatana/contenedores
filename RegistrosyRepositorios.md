# Registro
Un registro es un conjunto de repositorios publicos y/o privados que son indexados para faciltar
su comparticion.

Ejemplos de registros son:

https://registry.fedoraproject.org/
https://registry.access.redhat.com/
https://docker.io/

## Exploracion

```bash
$ sudo docker search fedora
$ sudo docker search mysql

```

## Estrellas :star: :star: :star:

Es la medida de calidad indicada por los usuarios, entre mas mejor

## Repositorios Trusted
Son repositorios de los cuales se certifica su confianza, por ejemplo, mantenidos por desarrolladores o gente de la comunidad
pero cuyo contenido no es compatible con algunas licencias del proyecto y no puede ser considerado contenido oficial.

## Repositorios Oficiales

Son repositorios firmados y que pertenecen oficialmente a los proyectos (usualmente son pagados) 

## login
```bash 
$ sudo docker login 
```
## Crear Repositorio

El docker hub hacer login y seguir los pasos del boton crear en el Dashboard

## Cambiar el registro por default en fedora
Editamos el archivo `/etc/containers/registries.conf`
y agregamos una entrada bajo **registries** con
```
 - docker.io
```
y reiniciamos el deminio docker para que tome los cambios:
```
$ sudo systemctl restart docker
```

## Generar una imagen simple


Primero es necesario crear un `Dockerfile` como el siguiente ejemplo:
```
FROM nginx

WORKDIR /usr/share/nginx/html

ADD ./index.html /usr/share/nginx/html

EXPOSE 80 
```
Despues crearemos la imagen de la siguiente forma:
```
$ sudo docker build -t <usuario>/<nombre>:<etiqueta> /direccion/al/Dockerfile
$ sudo docker build -t bt0dotninja/simpletest .
```
Si la construccion fue exitosa podremos enviarlo al repositorio
```
$ sudo docker push bt0dotninja/simpletest
```

Y ya sera posible compartirla con tus amigos :smile:

