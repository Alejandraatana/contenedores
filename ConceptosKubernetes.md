# Kubernetes

Kubernetes es un software que simplifica y autamtiza el proceso de despliegue de aplicaciones 
en contendedores y escalarlas (vertical y horizontal). Decimos que kubernetes orquesta el despliege de 
contendores y ademas esta diseñado para ser elastico, es decir si una aplicacacion requiere mas recursos
es posible porporcionarlos y reducirlos "on demand" (cuando sea necesario). 

Puesto esta hecho para funcionar en cluster y en "nube" por lo que requiere de alguna manera de identificar
y firmar que las imagenes, volumenes y contendores son los correctos, para esto uno de sus componentes
principales es __etcd__. __etcd__ es un almacenamientos ligero y distribuido de llaves/valores 
(como una tabla hash distribuida) que guarda las configuraciones propias de cada elemento disponible.

Cada nodo o Kubelet puede accesar a esta informacion mediante peticiones web o por la api de JSON diponible.

Ademas Kubernetes ofrece alta disponibildad (HA por high availabilty) lo que lo hace ideal para ser
parte de una infrestructura __seria__ de muchas empresas.

## Terminologia

* PODS: Si pensamos en una kubernetes como un rompecabezas el pod es una pieza sencilla del el y
por lo mismo son la pieza mas pequeña que se peude desplegar (poner en pruebas o produccion), cada pod tiene su propio
espacio de nombres y todos los contendores dentro del pod comparten:

  * Direccion IP
  * Espacio de puertos (si un contenedor ya tiene el puerto 80 otro no lo puede tener porque ya esta ocupado)
  * Se pueden encontrar o comunicar ligandoce con localhost
  * Se pueden comunicar mediante IPC (inter process comunicacion, comunicacion entre procesos, creo que se ve en sistemas operativos o distribuidos)
  * Pueden compartir volumenes.
  
El pod sirve par mantener y administrar contenderes que se requieren/ayudan unos otros como por ejemplo una aplicacion con su base de datos, nota que no necesariamente tienen que estar en el mismo equipo fisico y compartir el pod, es mas, es comun que esten separados.

* Labels: Atiquetas
