FROM sequenceiq/hadoop-docker:2.7.0
MAINTAINER wangjiong@britecloudtech.com
RUN echo root123 | passwd --stdin root
RUN yum install net-tools -y
CMD /etc/bootstrap.sh -d
