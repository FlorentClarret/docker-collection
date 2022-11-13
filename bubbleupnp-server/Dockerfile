FROM openjdk:jre-alpine

ENV FOLDER="/bubbleupnp-server/"

EXPOSE 58050/tcp 58051/tcp 1900/tcp 8200/tcp 5000/tcp

# hadolint ignore=DL3018
RUN apk --no-cache add iptables ffmpeg && \
    mkdir $FOLDER && \
    wget --progress=dot:giga -P $FOLDER http://www.bubblesoftapps.com/bubbleupnpserver/BubbleUPnPServer-distrib.zip && \
    unzip -d $FOLDER $FOLDER/BubbleUPnPServer-distrib.zip && \
    chmod +x $FOLDER/launch.sh && \
    rm $FOLDER/BubbleUPnPServer-distrib.zip && \
    rm $FOLDER/launch.bat && \
    rm $FOLDER/LICENCE.txt

CMD ["/bubbleupnp-server/launch.sh"]
