FROM wordpress:php7.2-fpm

COPY ./configs/local/php7.2.ini /usr/local/etc/php/php.ini
COPY ./configs/xdebug-2.9.6 /app/xdebug
RUN apt-get update && apt-get install -y \
curl \
mariadb-client \
wget \
zlib1g-dev \
libzip-dev \
unzip \
&& cd /app/xdebug/ \
&& phpize \
&& ./configure \
&& make \
&& mkdir -p /usr/local/lib/php/extensions/no-debug-non-zts-20190902/ \
&& cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20190902/ \


# Add WP-CLI
#RUN curl -o /bin/wp-cli.phar https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
#COPY ./wp-su.sh /bin/wp
#RUN chmod +x /bin/wp-cli.phar /bin/wp