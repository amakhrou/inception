FROM debian:bullseye

RUN apt-get update -y && apt-get upgrade -y \
    && apt-get install php-fpm php7.4-mysqlnd mariadb-client -y \
    && apt-get install curl wget -y

COPY ./conf/script.sh .

RUN chmod +x script.sh

CMD ["/script.sh"]