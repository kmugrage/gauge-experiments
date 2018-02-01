FROM gocd/gocd-agent-ubuntu-16.04:v18.1.0
LABEL maintainer="kmugrage@thoughtworks.com"

RUN apt-get update && apt-get install -y nodejs
RUN apt-get -y install sudo
RUN apt-get autoremove

COPY gauge-0.9.7-linux.x86_64.zip /tmp/

RUN unzip /tmp/gauge-0.9.7-linux.x86_64.zip -d /usr/local/bin

# Install needed gauge plugins for gauge
USER go
RUN /usr/local/bin/gauge install js
ENV PATH=$HOME/.gauge:$PATH

USER root
