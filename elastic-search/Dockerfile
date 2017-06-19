FROM docker.elastic.co/elasticsearch/elasticsearch:5.4.1
MAINTAINER hujun@kampus.com.cn

USER root
RUN echo root123 | passwd --stdin root
RUN yum install sudo -y
RUN yum install net-tools -y
RUN yum install passwd openssl openssh-server -y
RUN ssh-keygen -q -t rsa -b 2048 -f /etc/ssh/ssh_host_rsa_key -N ''
RUN ssh-keygen -q -t ecdsa -f /etc/ssh/ssh_host_ecdsa_key -N ''
RUN ssh-keygen -t dsa -f /etc/ssh/ssh_host_ed25519_key  -N ''
RUN echo "elasticsearch ALL=(ALL) NOPASSWD: ALL" >> /etc/sudoers
RUN echo elasticsearch | passwd --stdin elasticsearch

EXPOSE 22

ADD elasticsearch.yml /usr/share/elasticsearch/config/
ADD jvm.options /usr/share/elasticsearch/config/
USER root
RUN chown elasticsearch:elasticsearch config/elasticsearch.yml
RUN chown elasticsearch:elasticsearch config/jvm.options
USER elasticsearch


COPY docker-entrypoint.sh /
COPY prepare-exercise.sh /

ENTRYPOINT ["/docker-entrypoint.sh"]
CMD [""]
