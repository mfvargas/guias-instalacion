# Instalación de un servidor FTP en Ubuntu 18.04

## Documentación
* Guía de instalación: [How to setup FTP server on Ubuntu 18.04 Bionic Beaver with VSFTPD](https://linuxconfig.org/how-to-setup-ftp-server-on-ubuntu-18-04-bionic-beaver-with-vsftpd)

## Actualización del sistema
```terminal
$ sudo apt update
$ sudo apt upgrade -y
$ sudo reboot
```

## Instalación
```terminal
$ sudo apt install vsftpd
```

## Configuración
```terminal
# Respaldo del archivo de configuración
$ sudo cp /etc/vsftpd.conf  /etc/vsftpd.conf_default

# Edición del archivo de configuración
$ sudo nano /etc/vsftpd.conf
```

Contenido del archivo de configuración:
```
listen=NO
listen_ipv6=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
local_umask=022
dirmessage_enable=YES
use_localtime=YES
xferlog_enable=YES
connect_from_port_20=YES
chroot_local_user=YES
secure_chroot_dir=/var/run/vsftpd/empty
pam_service_name=vsftpd
rsa_cert_file=/etc/ssl/certs/ssl-cert-snakeoil.pem
rsa_private_key_file=/etc/ssl/private/ssl-cert-snakeoil.key
ssl_enable=NO
pasv_enable=Yes
pasv_min_port=10000
pasv_max_port=10100
allow_writeable_chroot=YES
```
