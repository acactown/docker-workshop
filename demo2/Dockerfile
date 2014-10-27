FROM ubuntu:12.04

MAINTAINER sameer@damagehead.com

RUN apt-get update
RUN apt-get install -y nginx zip curl

RUN echo "daemon off;" >> /etc/nginx/nginx.conf
RUN curl -o /usr/share/nginx/www/master.zip -L https://s3.amazonaws.com/docker-workshop/2048-master.zip \
    && /usr/share/nginx/www/ \
    && unzip master.zip \
    && mv 2048-master/* . \
    && rm -rf 2048-master master.zip

EXPOSE 80

CMD ["/usr/sbin/nginx", "-c", "/etc/nginx/nginx.conf"]
