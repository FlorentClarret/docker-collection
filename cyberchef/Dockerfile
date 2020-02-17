FROM node:10-buster

LABEL maintainer="florent.clarret@gmail.com"

WORKDIR /install/
USER root

RUN apt-get update && \
  apt-get install -y git && \
  rm -rf /var/lib/apt/lists/* && \
  npm install -g grunt-cli && \
  git clone https://github.com/gchq/CyberChef && \
  cd CyberChef && \
  npm install && \
  rm -rf /tmp/* /var/tmp/

EXPOSE 8080
WORKDIR /install/CyberChef
ENTRYPOINT ["grunt"]
CMD ["dev"]
