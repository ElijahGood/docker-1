FROM debian

RUN apt-get -y update
RUN apt-get -y upgrade
RUN apt-get install -y wget bzip2
RUN wget http://dl.4players.de/ts/releases/3.0.13.8/teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2
RUN tar xfvj teamspeak3-server_linux_amd64-3.0.13.8.tar.bz2

EXPOSE 9987/udp
EXPOSE 30033
EXPOSE 10011

ENTRYPOINT ["./teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# docker build -t ex01 .
# docker run -it --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01