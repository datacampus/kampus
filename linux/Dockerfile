FROM centos:latest
MAINTAINER wangjiong@britecloudtech.com
RUN echo root123 | passwd --stdin root
RUN sed -i  's/tsflags=nodocs/#tsflags=nodocs/g' /etc/yum.conf
RUN yum install net-tools -y
RUN yum install crontabs -y
RUN yum install man -y
RUN yum install man-pages -y
RUN yum install psmisc -y
RUN yum install passwd openssl openssh-server -y
RUN ssh-keygen -q -t rsa -b 2048 -f /etc/ssh/ssh_host_rsa_key -N '' 
RUN ssh-keygen -q -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N ''
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_ed25519_key  -N ''
EXPOSE 22
CMD /usr/sbin/sshd -D
