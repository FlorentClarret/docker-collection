FROM alpine:latest

LABEL maintainer="florent.clarret@gmail.com"

RUN apk --update upgrade && \
    apk add --update bind && \
    rm -rf /var/cache/apk/* && \
    mkdir /var/log/named

COPY config/* /etc/bind/

EXPOSE 53/udp

CMD ["named", "-c", "/etc/bind/named.conf", "-f"]