FROM debian:bullseye

RUN apt update && apt upgrade -y && apt install nginx openssl -y
RUN mkdir -p key
RUN openssl req -new -sha256 -newkey rsa:2048 -keyout key.pem -out /key/cert.pem -nodes -subj "/C=US/CN=www.msamhaou.fr"
COPY nginx.conf /etc/nginx/nginx.conf
RUN mkdir -p /var/www/wordpress
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;" ]