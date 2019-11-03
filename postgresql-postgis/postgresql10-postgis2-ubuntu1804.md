# Instalación de PostgreSQL 10 y PostGIS 2 en Ubuntu 18.04
**Última actualización**: 2 de noviembre de 2019

## Actualización del sistema
```terminal
$ sudo apt update
$ sudo apt upgrade -y
$ sudo reboot
```

## Revisión de las versiones disponibles
Comando apt-cache madison
```terminal
$ sudo apt-cache madison postgresql postgresql-contrib postgis postgresql-10-postgis-scripts
```
Salida
```terminal
postgresql |     10+190 | http://mirrors.digitalocean.com/ubuntu bionic/main amd64 Packages
postgresql-contrib |     10+190 | http://mirrors.digitalocean.com/ubuntu bionic/main amd64 Packages
   postgis | 2.4.3+dfsg-4 | http://mirrors.digitalocean.com/ubuntu bionic/universe amd64 Packages
postgresql-10-postgis-scripts | 2.4.3+dfsg-4 | http://mirrors.digitalocean.com/ubuntu bionic/universe amd64 Packages
```

## Instalación
```terminal
$ sudo apt update -y
$ sudo apt install -y postgresql postgresql-contrib postgis postgresql-10-postgis-scripts
```

## Revisión del servicio
```terminal
$ systemctl status postgresql.service
```
