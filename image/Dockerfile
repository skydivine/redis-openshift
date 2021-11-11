FROM centos

# RUN yum update -y && yum upgrade -y

RUN yum install -y https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
# COPY epel-7.repo  /etc/yum.repos.d/epel.repo
RUN yum install redis hostname -y ; yum clean all

COPY redis-master.conf /redis-master/redis.conf
COPY redis-slave.conf /redis-slave/redis.conf
RUN mkdir -p /redis-sentinel ; chmod -R 777 /redis-sentinel /redis-slave
COPY run.sh /run.sh

CMD [ "/run.sh" ]

ENTRYPOINT [ "bash", "-c" ]
