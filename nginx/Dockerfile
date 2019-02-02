FROM nginx:alpine

LABEL maintainer="florent.clarret@gmail.com"

RUN set -xe && \
    apk add --update --no-cache  \
    curl \
    rm -rf /tmp/* /var/tmp/

RUN rm /etc/nginx/conf.d/default.conf

COPY config/services.conf /etc/nginx/conf.d/
COPY config/nginx.conf /etc/nginx/

HEALTHCHECK --interval=1m --timeout=3s CMD curl --fail http://localhost/health-check.html || exit 1