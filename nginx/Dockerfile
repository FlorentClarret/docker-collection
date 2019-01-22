FROM nginx:alpine

LABEL maintainer="florent.clarret@gmail.com"

RUN rm /etc/nginx/conf.d/default.conf

COPY config/services.conf /etc/nginx/conf.d/
COPY config/nginx.conf /etc/nginx/