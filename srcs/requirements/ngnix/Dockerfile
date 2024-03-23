FROM debian:bullseye
RUN apt-get update && apt-get upgrade
RUN apt-get install -y nginx openssl

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt -subj "/C=MA/ST=KH/L=KHOURIBGA/O=1337/OU=42network"
COPY ./conf/default.conf /etc/nginx/sites-enabled/default





EXPOSE 443
EXPOSE 80


CMD ["nginx", "-g", "daemon off;"]