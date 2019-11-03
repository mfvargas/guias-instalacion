# Instalación de PostgreSQL 10 y PostGIS 2 en Ubuntu 18.04

## Actualización del sistema
```terminal
$ sudo apt update
$ sudo apt upgrade -y
$ sudo reboot
```

## Revisión de las versiones disponibles
```terminal
$ sudo apt-cache madison postgresql postgis
```
Salida
```terminal
postgresql |     10+190 | http://mirrors.digitalocean.com/ubuntu bionic/main amd64 Packages
   postgis | 2.4.3+dfsg-4 | http://mirrors.digitalocean.com/ubuntu bionic/universe amd64 Packages
```

## Instalación
```terminal
$ sudo apt update -y
$ sudo apt install -y postgresql postgresql-contrib postgis postgresql-10-postgis-2.5-scripts
```
