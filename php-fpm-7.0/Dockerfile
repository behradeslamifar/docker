FROM ubuntu:16.04
MAINTAINER Behrad Eslamifar <b.eslamifar@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
RUN apt-get update 
RUN apt-get install -y apt-utils && apt-get clean
RUN apt-get install -y tzdata locales && apt-get clean
RUN /bin/cp /usr/share/zoneinfo/Asia/Tehran /etc/localtime
RUN /bin/echo "Asia/Tehran" > /etc/timezone

RUN /usr/sbin/locale-gen en_US.UTF-8
RUN /usr/sbin/locale-gen fa_IR


RUN apt-get install -y php php-bcmath php-cli php-fpm php-gd php-intl php-mbstring php-mysqlnd php-mysql php-opcache php-pdo php-pear php-igbinary php-json php-memcache php-memcached php-msgpack php-redis php-zip php-gettext php-soap php-tcpdf php-tidy php-xml php-xmlrpc && apt-get clean

RUN mkdir -p /run/php
COPY www.conf /etc/php/7.0/fpm/pool.d/

CMD ["/usr/sbin/php-fpm7.0","--nodaemonize","--fpm-config","/etc/php/7.0/fpm/php-fpm.conf"]
