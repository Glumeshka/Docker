FROM ubuntu
RUN apt-get update
RUN apt-get install -y nginx
COPY ./application.local.conf /etc/nginx/sites-enabled/application.local.conf
WORKDIR /data
VOLUME /data
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;" ]