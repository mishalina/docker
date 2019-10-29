# THE TASK
# From a debian image you will add the appropriate sources to create a 
# TeamSpeak server, that will launch along with your container. It will be 
# deemed valid if at least one user can connect to it and engage in a normal 
# discussion (no far-fetched setup), so be sure to create your Dockerfile with 
# the right options. Your program should get the sources when it builds, they 
# cannot be in your repository.

# NOTES
# https://hub.docker.com/_/teamspeak
# https://forum.teamspeak.com/threads/132611-Install-teamspeak-3-server-on-Debian-8

FROM debian

MAINTAINER  abooster <abooster@student.21-school.ru>
ENV TS3SERVER_LICENSE=accept
WORKDIR /home/teamspeak
EXPOSE 9987/udp 10011 30033

RUN apt-get update && apt-get upgrade -y
RUN apt-get install wget bzip2 -y
RUN wget http://files.teamspeak-services.com/releases/server/3.9.1/teamspeak3-server_linux_amd64-3.9.1.tar.bz2
RUN tar -xvf teamspeak3-server_linux_amd64-3.9.1.tar.bz2

WORKDIR teamspeak3-server_linux_amd64

ENTRYPOINT ./ts3server
# docker build 
# run
# docker run --name ts3serv --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ID_IMAGE

