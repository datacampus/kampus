FROM sequenceiq/hadoop-docker:2.7.0
MAINTAINER wangjiong@britecloudtech.com
RUN yum install net-tools -y
RUN echo root123 | passwd --stdin root
CMD /etc/bootstrap.sh -d
