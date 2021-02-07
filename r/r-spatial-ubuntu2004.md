# Instalación de R en Ubuntu 20.04

## Recursos
* [How To Install R on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-r-on-ubuntu-20-04)
* [Installation of R 4.0 on Ubuntu 20.04 LTS and tips for spatial packages](https://rtask.thinkr.fr/installation-of-r-4-0-on-ubuntu-20-04-lts-and-tips-for-spatial-packages/)

## Instalación de la base de R
```shell
# Repositorios para R base
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
$ sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu focal-cran40/'
$ sudo apt update

# Instalación de R base
$ sudo apt install r-base r-base-core r-recommended r-base-dev

# Respositorio UbuntuGIS PPA para bibliotecas espaciales
$ sudo add-apt-repository ppa:ubuntugis/ubuntugis-unstable
$ sudo apt update

# Instalación de GDAL, PROJ, GEOS y otras bibliotecas espaciales generales
$ sudo apt libgdal-dev libproj-dev libgeos-dev install libudunits2-dev

# Se ejecuta con sudo para que los paquetes que se instalen estén disponibles para todos los usuarios
$ sudo -i R
```

## Instalación de paquetes
```shell
> install.packages('txtplot')
> library('txtplot')
> txtplot(cars[,1], cars[,2], xlab = 'speed', ylab = 'distance')
```
