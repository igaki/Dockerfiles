FROM samalba/docker-registry

MAINTAINER igaki version:0.1

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list

# Hack for initctl not being available in Ubuntu
RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl

RUN apt-get update
RUN apt-get upgrade -y

RUN apt-get install -y openssh-server
RUN mkdir /var/run/sshd
RUN /usr/sbin/sshd

RUN echo 'root:newpassword' | chpasswd

ADD ./run.sh /docker-registry/
RUN chmod +x /docker-registry/run.sh

EXPOSE 5000
EXPOSE 22

CMD ["/bin/sh","-c","cd /docker-registry && ./setup-configs.sh && ./run.sh"]