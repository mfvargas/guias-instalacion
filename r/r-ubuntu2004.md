# Instalación de R en Ubuntu 20.04

## Recursos
* [How To Install R on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-r-on-ubuntu-20-04)

## Instalación de la base de R
```shell
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
$ sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'
$ sudo apt update
$ sudo apt install r-base

# Se ejecuta con sudo para que los paquetes que se instalen estén disponibles para todos los usuarios
$ sudo -i R
```

## Instalación de paquetes
```shell
> install.packages('txtplot')
> library('txtplot')
> txtplot(cars[,1], cars[,2], xlab = 'speed', ylab = 'distance')
```
