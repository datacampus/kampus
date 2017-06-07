FROM centos:latest
MAINTAINER wangjiong@britecloudtech.com
RUN echo root123 | passwd --stdin root
RUN yum install net-tools -y
RUN yum install passwd openssl openssh-server -y
RUN ssh-keygen -q -t rsa -b 2048 -f /etc/ssh/ssh_host_rsa_key -N '' 
RUN ssh-keygen -q -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N ''
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_ed25519_key  -N ''
CMD /usr/sbin/sshd -D
