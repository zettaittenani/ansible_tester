FROM centos:7.5.1804
MAINTAINER "zettaittenani<zettaittenani@gmail.com>"

# infra settings
RUN yum check
RUN yum -y update
RUN yum -y install openssh-clients

# application settings
RUN curl -L https://bootstrap.pypa.io/get-pip.py | python
RUN pip install ansible

CMD /sbin/init
