FROM debian:bullseye

RUN apt-get update && apt-get upgrade
RUN apt-get install -y mariadb-server mariadb-client

COPY  ./conf/startdb.sh /
RUN chmod +x /startdb.sh

EXPOSE 3306

CMD ["/startdb.sh"]
