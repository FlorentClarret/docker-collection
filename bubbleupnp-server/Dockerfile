FROM openjdk:jre-alpine

MAINTAINER Florent Clarret <florent.clarret@gmail.com>

ENV FOLDER="/bubbleupnp-server/"

EXPOSE 58050/tcp 58051/tcp 1900/tcp 8200/tcp 5000/tcp

RUN apk --update add iptables ffmpeg && \
    mkdir $FOLDER && \
    wget -P $FOLDER http://www.bubblesoftapps.com/bubbleupnpserver/BubbleUPnPServer-distrib.zip && \
    unzip -d $FOLDER $FOLDER/BubbleUPnPServer-distrib.zip && \
    chmod +x $FOLDER/launch.sh && \
    rm $FOLDER/BubbleUPnPServer-distrib.zip && \
    rm $FOLDER/launch.bat && \
    rm $FOLDER/LICENCE.txt

CMD ["/bubbleupnp-server/launch.sh"]
