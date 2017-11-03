# MiniKube :hamster:

Minicube es una instancia de pruebas para aplicaciones dentro de kubernetes, es usada para desarrollo y permite disfrutar del uso
de las kubernetes sin configurar un cluster.

## Instalacion de docker-machine
```bash
curl -L https://github.com/docker/machine/releases/download/v0.13.0/docker-machine-`uname -s`-`uname -m` >/tmp/docker-machine &&
    chmod +x /tmp/docker-machine &&
    sudo cp /tmp/docker-machine /usr/local/bin/docker-machine
```
## Instalacion driver kvm para docker machine
```
  curl -L https://github.com/dhiltgen/docker-machine-kvm/releases/download/v0.10.0/docker-machine-driver-kvm-centos7 > /tmp/docker-machine-driver-kvm &&  chmod +x /tmp/docker-machine-driver-kvm && sudo mv /tmp/docker-machine-driver-kvm /usr/local/bin/docker-machine-driver-kvm
```

## Instalar Minikube
```bash
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/
```

## Ejecutar Minikube
```bash
$ minikube start --vm-driver=kvm
$ kubectl config use-context minikube
$ kubectl cluster-info
```
### Ejercicio: Crear una aplicacion web dentro de un contendor docker
> Puedes usar alguna trabajada previemente :trollface:

## Correr aplicacion en cluster
```bash
$ kubectl run hamster --image=imagenDeHamster --port 80
$ kubectl get deployments
$ kubectl get pods
$ kubectl config view
```
## Publicar la aplicacion
```bash
$ kubectl expose deployment hamster --type=LoadBalancer
$ minikube service hamster
```
