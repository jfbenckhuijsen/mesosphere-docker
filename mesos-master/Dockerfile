FROM quay.io/salvesdevelopment/mesos-base

MAINTAINER Justin Plock <justin@plock.net>
MAINTAINER Jeroen Benckhuijsen <jeroen.benckhuijsen@salvesdevelopment.nl>

# Not exposing port b/c you have to run the master in bridge net mode
#EXPOSE 5050

RUN mkdir /etc/service/mesos-master
ADD run.sh /etc/service/mesos-master/run
RUN chmod +x /etc/service/mesos-master/run
