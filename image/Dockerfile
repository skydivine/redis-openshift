FROM centos

RUN yum update && yum upgrade

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-8.noarch.rpm
 
RUN yum install redis hostname -y ; yum clean all

COPY redis-master.conf /redis-master/redis.conf
COPY redis-slave.conf /redis-slave/redis.conf
RUN mkdir -p /redis-sentinel ; chmod -R 777 /redis-sentinel /redis-slave
COPY run.sh /run.sh

CMD [ "/run.sh" ]

ENTRYPOINT [ "bash", "-c" ]
