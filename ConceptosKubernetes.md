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

* __PODS__: Si pensamos en una kubernetes como un rompecabezas el pod es una pieza sencilla del el y
por lo mismo son la pieza mas pequeña que se peude desplegar (poner en pruebas o produccion), cada pod tiene su propio
espacio de nombres y todos los contendores dentro del pod comparten:

  * Direccion IP
  * Espacio de puertos (si un contenedor ya tiene el puerto 80 otro no lo puede tener porque ya esta ocupado)
  * Se pueden encontrar o comunicar ligandoce con localhost
  * Se pueden comunicar mediante IPC (inter process comunicacion, comunicacion entre procesos, creo que se ve en sistemas operativos o distribuidos)
  * Pueden compartir volumenes.
  
El pod sirve par mantener y administrar contenderes que se requieren/ayudan unos otros como por ejemplo una aplicacion con su base de datos, nota que no necesariamente tienen que estar en el mismo equipo fisico y compartir el pod, es mas, es comun que esten separados.

* __Labels (Atiquetas)__: Son un concepto simple pero importante en kubernetes, las labels son pares de llave/valor
que se incorporan a objetos en kubernetes (por ejemplo un pod). Esto permite especificar atributos unicos a
objetos que ademas tienen sentido para las personas (por ejemplo el nombre del contendor contra su id).
por ejemplo podemos identificar:
  * Versiones de Software: Alpha, beta, estable, etc.
  * Entornos: Desarrollo y produccion.
  * Tier: Front-end o Back-end.
Las etiquetas son muy flexibles y se peuden aplicar para nombrar cualquier cosa, no solo las anteriores.

 * __Replica sets (Conjuntos de replica)__: Se encargan de la planificacion y replanificacion automatica
 de tal forma que un conjunto de pods (llamados replicas) esten activos en todo momento. Si tu aplicacion requiere
 dos contendores de frontend y 3 de backend, los preplica sets se encargan de siempre sea asi y ademas permite
 escalar tanto hacia arriba como hacia abajo.
 
 * __Deployments__: Son un concepto importante en kubernetes, son la forma declarativa (secuencia de instrucciones)
 que permiten poner en marcha la aplicacion. Dado que son instruciones basicamente programas como debe funcionar tu infraestructura.
 Los deployments siguen el principio de idenpodencia de tal manera que las declaras una vez y las usas muchas :octocat:
 
 ## Instalacion en fedora
 ```bash
 $ sudo dnf install kubernetes
 ```
 Adicionalmente y para usar maquinas virtuales mas adelante:
 ```bash
 $ sudo dnf install libvirt-daemon-kvm kvm
 $ sudo usermod -a -G libvirt $(whoami)
 $ sudo newgrp libvirt
 ```
 
