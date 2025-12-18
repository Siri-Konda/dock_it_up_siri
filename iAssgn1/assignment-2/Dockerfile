FROM nginx:latest

RUN apt-get update && apt-get install -y curl

COPY index.html /usr/share/nginx/html/index.html
COPY api.html /usr/share/nginx/html/api.html
COPY default.conf /etc/nginx/conf.d/default.conf
