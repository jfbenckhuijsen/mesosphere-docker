#FROM garland/mesosphere-docker-base-image

# Install mesos.
#RUN sudo apt-get -y install mesos marathon deimos

#EXPOSE 8080

#CMD ["java", "-Xmx512m", "-Djava.library.path=/usr/local/lib", "-Djava.util.logging.SimpleFormatter.format='%2$s %5$s%6$s%n'", "-cp", "/usr/local/bin/marathon", "mesosphere.marathon.Main", "--zk", "$MESOS_ZK", "--master", "$MESOS_MASTER"]

# Source: https://github.com/mesosphere/marathon/blob/fbf627fad91e7d00b0a96d29ad35f7f4bf21507d/Dockerfile

# Marathon Dockerfile
FROM phusion/baseimage:0.9.17
MAINTAINER Justin Plock <justin@plock.net>
MAINTAINER Jeroen Benckhuijsen <jeroen.benckhuijsen@salvesdevelopment.nl>
MAINTAINER Mesosphere <support@mesosphere.io>

## DEPENDENCIES ##
RUN echo "deb http://repos.mesosphere.io/ubuntu/ trusty main" > /etc/apt/sources.list.d/mesosphere.list
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF
RUN apt-get update
RUN apt-get install --assume-yes mesos python-software-properties curl default-jdk

## MARATHON ##
ADD http://downloads.mesosphere.io/marathon/marathon-0.11.1/marathon-0.11.1.tgz /tmp/marathon.tgz
RUN mkdir -p /opt/marathon && tar xzf /tmp/marathon.tgz -C /opt/marathon --strip=1 && rm -f /tmp/marathon.tgz

EXPOSE 8080

# Add baseimage-docker service file
RUN mkdir /etc/service/mesos-marathon
ADD run.sh /etc/service/mesos-marathon/run
RUN chmod +x /etc/service/mesos-marathon/run

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]
