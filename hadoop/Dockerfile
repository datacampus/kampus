FROM sequenceiq/hadoop-docker:2.7.0
MAINTAINER wangjiong@britecloudtech.com
RUN echo root:root123|chpasswd
RUN sed -i 's/2122/22/g' /etc/ssh/sshd_config
EXPOSE 22
CMD /etc/bootstrap.sh -d
