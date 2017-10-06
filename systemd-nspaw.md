# systemd lightweight containers :octocat:

```
$ sudo dnf -y install systemd-container
```

## Contenedor Fedora
```
$ mkdir fedora-hamster
$ sudo dnf -y --releasever=26 --nogpg --installroot=/home/hamster/fedora-hamster --disablerepo='*' --enablerepo=fedora install systemd passwd dnf fedora-release vim-minimal
$ sudo systemd-nspawn -D /home/hamster/fedora-hamster
# passwd
...
ctrl + c
$ sudo systemd-nspawn -bD /home/hamster/fedora-hamster 3 
```


## Contenedor Debian

```
$ sudo dnf -y install debootstrap
$ mkdir debian-hamster
$ sudo debootstrap --arch=i386 testing ./debian-hamster
$ sudo systemd-nspawn --directory=./debian-hamster passwd
$ sudo systemd-nspawn --directory=./debian-hamster useradd soyunhamstercacheton
$ sudo systemd-nspawn -D ./debian apt-get update
$ sudo systemd-nspawn -D ./debian apt-get install default-jre ssh firefox
$ sudo systemd-nspawn -bD ./debian-hamster --bind ~/Downloads:/mnt:rbind 
```
