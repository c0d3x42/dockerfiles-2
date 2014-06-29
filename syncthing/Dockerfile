FROM ubuntu:trusty

MAINTAINER Scott Hansen <firecat4153@gmail.com>

RUN apt-get update && apt-get install -qy supervisor
ADD supervisord.conf /etc/supervisor/conf.d/supervisord.conf
RUN useradd --no-create-home -g users firecat53
ADD https://github.com/calmh/syncthing/releases/download/v0.8.17/syncthing-linux-amd64-v0.8.17.tar.gz /syncthing.tar.gz
RUN tar -xzvf syncthing.tar.gz && mv sync*/syncthing /syncthing && rm syncthing.tar.gz

EXPOSE 8080 22000

CMD ["/usr/bin/supervisord"]