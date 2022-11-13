# hadolint ignore=DL3007
FROM alpine:latest
LABEL maintainer="florent.clarret@gmail.com"

# hadolint ignore=DL3018
RUN set -xe && \
    apk add --update --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/testing \
    smartmontools \
    msmtp \
    mailx \
    ca-certificates && \
    rm -rf /tmp/* /var/tmp/ && \
    ln -sf /usr/bin/msmtp /usr/sbin/sendmail

COPY config/smartd.conf /etc/smartd.conf
COPY config/msmtprc /etc/msmtprc
COPY config/aliases /etc/aliases

ENTRYPOINT ["/usr/sbin/smartd", "--debug"]
