# Espacio de Nombres en Docker

Docker mantiene un conjunto de nombres que identifican de manera unica un contendor en ejecucion. Docker utiliza el espacio de nombres y cgroups de linux para tener los espacios de trabajos separados en cada contendor.
Este conjunto incluye un nombre leible por los humanos, este es especificado con `--name` y en caso
de omitirlo tomara un nombre contruido como `Adjetivo_Cientifico/Ingeniero` al azar.

Ademas incluira una cadena hash que identifica de manera unica al contenedor, por ejemplo:
```bash
$ CID = $(sudo docker create busybox)
$ echo $CID
85bd6faa20cd9f1cbedf930f1ade822cb87c7d10c1e6ab6a02a968763c352bdd
```
## Ejercicio 1
* Identifica los componentes del nombre en un contendedor en ejecucion.
* Genera un contenedor sin nombre fijado por el usuario.
* Genera un contendor llamado hamster.

## Ejercicio 2
* Genera 100 contendores **sin** nombre fijo de tipo busybox que se terminen de ejecutar con una diferencia de 5 segundos. 
* Genera 100 contendores **con** nombre fijo de tipo busybox que se terminen de ejecutar con una diferencia de 5 segundos.

## Ejercicio 3
* Crea un contenedor busybox que se ejecute durante 300 segundos y lista sus procesos internos.
* Creo otro contendor identico al anterior pero agrega la opcion `--pid host`
