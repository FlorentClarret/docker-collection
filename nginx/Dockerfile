FROM nginx:alpine

LABEL maintainer="florent.clarret@gmail.com"

RUN rm /etc/nginx/conf.d/default.conf

COPY services.conf /etc/nginx/conf.d/
COPY nginx.conf /etc/nginx/