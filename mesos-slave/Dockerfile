FROM quay.io/salvesdevelopment/mesos-base

MAINTAINER Justin Plock <justin@plock.net>
MAINTAINER Jeroen Benckhuijsen <jeroen.benckhuijsen@salvesdevelopment.nl>

RUN mkdir /etc/service/mesos-slave
ADD run.sh /etc/service/mesos-slave/run
RUN chmod +x /etc/service/mesos-slave/run
