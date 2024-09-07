FROM debian:bullseye

RUN apt-get update -y && apt-get upgrade -y \
    && apt-get install -y nginx openssl

RUN mkdir -p /etc/nginx/ssl

RUN openssl req -newkey rsa:4096 -x509 -sha256 -days 365 -nodes \
       -out /etc/nginx/ssl/amakhrou.crt \
       -keyout /etc/nginx/ssl/amakhrou.key \
       -subj "/C=FR/ST=BENGUERIR/L=BENGUERIR/O=42 School/OU=amakhrou/CN=amakhrou/"

COPY conf/nginx.conf /etc/nginx/conf.d

CMD ["nginx", "-g", "daemon off;"]