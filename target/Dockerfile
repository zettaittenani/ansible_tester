FROM centos:7.5.1804
MAINTAINER "zettaittenani"

# infra settings
RUN yum check
RUN yum -y update
RUN yum -y install openssh-server
RUN sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed -ri 's/^UsePAM yes/UsePAM no/' /etc/ssh/sshd_config
RUN passwd -d root

# start sshd when booting
RUN /bin/systemctl enable sshd
EXPOSE 22

CMD /sbin/init
