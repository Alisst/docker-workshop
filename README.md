FROM ubuntu:latest
MAINTAINER Ali Huzmeli <alihuzmeli@hotmail.com>

#Paket listelerini download et
RUN apt-get update

#Nginx paketini yükle
RUN apt-get install -y nginx

ADD [ "/src/index.html", "/var/www/html/" ]

EXPOSE 80

ENTRYPOINT nginx -g 'daemon off;'

