## build command (at Dockerfile dir)
# docker build ./ -t ansible-controller:latest
## run command
# docker run --privileged -d -p 121:22 --name controller ansible-controller:latest

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

# application settings
RUN yum -y install git
RUN curl -L https://bootstrap.pypa.io/get-pip.py | python
RUN pip install ansible

# start sshd when booting
RUN /bin/systemctl enable sshd
EXPOSE 22

CMD /sbin/init