# Sen
Sen es una interfaz de usuario para manejar contendores desde linea de comandos

## Instalacion
```bash
$ sudo dnf install sen
```

# Atajos de Teclado

El autor de `sen` se declara Fan de `Vim` por lo que  trata que sus atajos sean parecidos... No lo son tanto.

## Globales

```
/         busqueda
n         siguiente ocurrencia
N         Ocurrencia previa
f4        Muestra solo las lineas con la ocurrencia de la busqueda
f5        Abre un arbol de imagenes
ctrl o    Va al siguiente buffer o pagina
ctrl i    Regresa al buffer o pagin anterior
x         Borra buffer
q         borra buffer, sale so no hay mas
ctrl l    redibuja la interfaz
h, ?      muestra ayuda
:         Inicia el promt de comandos
```

## Movimiento

```
gg, home  va al primer item
G, end    va al ultimo item
j         Abajo
k         arriba
pg up
ctrl u    va 10 lineas arriba
pg down
ctrl d    va 10 lineas abajo
```

## Listing

```
@         refresca listado
f4        filtrado
```

## Comandos de Imagen

```
i         inspecciona imagen
d         borra imagen (irreversible!)
enter     Muestra informacion detallada
```

## Comandos de contendor

```
i         inspecciona contenedor
l         muestra logs del contendor
f         sigue los logs del container
d         borra contenedor (irreversible!)
t         detiene contenedor
s         inicia contendor
r         reinicia contenedor
p         pausa contenedor
u         continua contenedor
b         Abre puertos mapeados en el navegador 
X         Mata contenedor
!         Habilita/deshabilita vista dinamica
```

## Imagen/contendor info buffer

```
enter     Muestra informacion detallada
i         inspecciona imagen o contenedor
```
