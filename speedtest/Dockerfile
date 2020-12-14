FROM debian:buster-slim

RUN apt-get update && \ 
    apt-get install -y gnupg1 apt-transport-https dirmngr

ENV INSTALL_KEY=379CE192D401AB61
COPY speedtest.list /etc/apt/sources.list.d/speedtest.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys $INSTALL_KEY && \
    apt-get update && \
    apt-get install -y speedtest

RUN useradd -m speedtest
USER speedtest

ENTRYPOINT ["speedtest", "--accept-license", "--accept-gdpr"]