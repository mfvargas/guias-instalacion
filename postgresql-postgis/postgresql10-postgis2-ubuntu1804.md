# Instalación de PostgreSQL 10 y PostGIS 2 en Ubuntu 18.04
**Última actualización**: 2 de noviembre de 2019

## Actualización del sistema
```terminal
$ sudo apt update
$ sudo apt upgrade -y
$ sudo reboot
```

## Revisión de las versiones disponibles
```terminal
$ sudo apt-cache madison postgresql postgresql-contrib postgis postgresql-10-postgis-scripts
```
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
```terminal
● postgresql.service - PostgreSQL RDBMS
   Loaded: loaded (/lib/systemd/system/postgresql.service; enabled; vendor preset: enabled)
   Active: active (exited) since Sun 2019-11-03 03:14:32 UTC; 18min ago
 Main PID: 5306 (code=exited, status=0/SUCCESS)
    Tasks: 0 (limit: 4915)
   CGroup: /system.slice/postgresql.service
```

```terminal
$ systemctl status postgresql@10-main.service
```
```terminal
● postgresql@10-main.service - PostgreSQL Cluster 10-main
   Loaded: loaded (/lib/systemd/system/postgresql@.service; indirect; vendor preset: enabled)
   Active: active (running) since Sun 2019-11-03 03:14:37 UTC; 18min ago
 Main PID: 6511 (postgres)
    Tasks: 7 (limit: 4915)
   CGroup: /system.slice/system-postgresql.slice/postgresql@10-main.service
           ├─6511 /usr/lib/postgresql/10/bin/postgres -D /var/lib/postgresql/10/main -c config_file=/etc/postgresql/10/main/postgresql.conf
           ├─6519 postgres: 10/main: checkpointer process
           ├─6520 postgres: 10/main: writer process
           ├─6521 postgres: 10/main: wal writer process
           ├─6522 postgres: 10/main: autovacuum launcher process
           ├─6523 postgres: 10/main: stats collector process
           └─6526 postgres: 10/main: bgworker: logical replication launcher
```

```terminal
$ systemctl is-enabled postgresql
```
```terminal
enabled
```

## Modificación de archivos de configuración
Modificación de postgresql.conf
```terminal
$ sudo nano /etc/postgresql/10/main/postgresql.conf
```
```terminal
# Descomentar y cambiar la línea
listen_addresses = 'localhost'
# Por
listen_addresses = '*'
# Guardar y salir
```

Modificación de pg_hba.conf
```terminal
$ sudo nano /etc/postgresql/10/main/pg_hba.conf
```
```terminal
# Añadir la siguiente línea (en la sección de IPv4) para dar acceso a todos las direcciones IP
host     all     all        0.0.0.0/0      md5
# Guardar y salir
```

Reinicio del PostgreSQL
```terminal
$ sudo service postgresql restart
```
