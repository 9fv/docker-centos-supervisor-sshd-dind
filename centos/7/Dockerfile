FROM orboan/docker-centos-supervisor-ssh
MAINTAINER fmichaud@9fevrier.com

COPY adds/etc/supervisor.d/docker-service.conf /etc/supervisor.d/docker-service.conf

ENV DOCKER_CHANNEL edge
ENV DOCKER_VERSION 18.05.0-ce
ENV ARCH x86_64

WORKDIR /root

RUN yum update -y \
    && curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${ARCH}/docker-${DOCKER_VERSION}.tgz" \
    && tar --extract \
      --file docker.tgz \
      --strip-components 1 \
      --directory /usr/bin/ \
  && rm -f docker.tgz \
  && dockerd -v \
  && docker -v \
  && mkdir -p /var/log/supervisor \
  && yum clean all -y \
  && rm -rf /var/cache/yum/*
