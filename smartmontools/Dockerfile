FROM alpine:latest
LABEL maintainer="florent.clarret@gmail.com"

RUN set -xe && \
    apk add --update --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing \
    smartmontools \
    msmtp \
    mailx \
    ca-certificates && \
    rm -rf /tmp/* /var/tmp/ && \
    ln -sf /usr/bin/msmtp /usr/sbin/sendmail

ADD config/smartd.conf /etc/smartd.conf
ADD config/msmtprc /etc/msmtprc
ADD config/aliases /etc/aliases

CMD /usr/sbin/smartd --debug
