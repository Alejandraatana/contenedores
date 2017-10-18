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

## Mount y volume

Aunque comparten practicamente las mismas caracteristicas volume (`--volume -v`) puede ser depreciado pronto y substituido por mount completamente en el manejo de volumenes.

## Mount Sintaxis

```
$ sudo docker 
```
