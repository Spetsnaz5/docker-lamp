# PHP8.3
FROM ubuntu:20.04

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y software-properties-common \
    && add-apt-repository ppa:ondrej/php

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
    php8.3 \
    php8.3-cli php8.3-fpm php8.3-mysql php8.3-xml php8.3-mbstring php8.3-curl \
    php8.3-zip php8.3-gd \
    libapache2-mod-php8.3 \
    vim \
    && a2enmod php8.3

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y \
    curl \
    php-cli \
    unzip \
    && curl -sS https://getcomposer.org/installer -o composer-setup.php \
    && php composer-setup.php --install-dir=/usr/local/bin --filename=composer

COPY index.php /var/www/html/index.php

#EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]