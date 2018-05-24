#docker build -t teamspeak-im .
#docker run -it -p 9987:9987/udp -p 10011:10011 -p 30033:30033 teamspeak-im
FROM debian
EXPOSE 9987 10011 30033
ENV TS3SERVER_LICENSE=accept
RUN apt-get -y update && apt-get -y upgrade && apt-get install -y nano && apt-get install -y wget && apt-get install -y bzip2 && apt-get install -y systemd && wget http://dl.4players.de/ts/releases/3.0.13.6/teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 && tar xvfj teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2 && rm -rf teamspeak3-server_linux_amd64-3.0.13.6.tar.bz2
WORKDIR teamspeak3-server_linux_amd64
CMD ["bash", "-c",  "sh ts3server_startscript.sh start; bash"]