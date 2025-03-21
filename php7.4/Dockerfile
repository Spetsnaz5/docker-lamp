# PHP7.4
FROM ubuntu:20.04

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y \
    apache2 \
    php7.4 \
    libapache2-mod-php7.4 \
    php7.4-mysql \
    vim \
    && rm -rf /var/lib/apt/lists/*

RUN sed -i 's/AllowOverride None/AllowOverride All/' /etc/apache2/apache2.conf

COPY index.php /var/www/html/index.php

#VOLUME ["/storage1", "/storage2", "/storage2"]

#EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]