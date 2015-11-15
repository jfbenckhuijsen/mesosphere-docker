FROM phusion/baseimage:0.9.17

# Install dependancies
RUN DISTRO=$(lsb_release -is | tr '[:upper:]' '[:lower:]'); CODENAME=$(lsb_release -cs); echo "deb http://repos.mesosphere.io/${DISTRO} ${CODENAME} main" | sudo tee /etc/apt/sources.list.d/mesosphere.list
RUN sudo apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF
RUN sudo apt-get -y update
RUN sudo apt-get -y install curl python-setuptools python-pip python-dev python-protobuf

# Use baseimage-docker's init system.
CMD ["/sbin/my_init"]
