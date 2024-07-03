FROM debian:bullseye

RUN apt-get update && apt-get upgrade
RUN apt-get install -y nginx openssl

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt -subj "/C=MA/ST=KH/L=KHOURIBGA/O=1337/OU=42network"
COPY ./conf/default.conf /etc/nginx/sites-enabled/default


# Expose the port that the app runs on (hit to the user about which ports the application inside the container is using, for documentation)
EXPOSE 443

# instruction sets the default command to run when the container starts
# which will also run in the working dcirectory if specified.
CMD ["nginx", "-g", "daemon off;"]