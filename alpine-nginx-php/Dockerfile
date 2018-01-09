FROM alpine:3.6

RUN set -xe && \
    apk upgrade --update && \
    apk add --no-cache \
        php7 php7-fpm php7-mysqli php7-json php7-openssl php7-curl \
        php7-zlib php7-xml php7-phar php7-intl php7-dom php7-xmlreader php7-ctype \
        php7-mbstring php7-gd nginx supervisor curl \
    && \
    mkdir -p /var/www/html && \
    echo "<?php echo phpinfo(); ?>" > /var/www/html/index.php && \
    touch /var/log/lastlog

COPY config/nginx.conf /etc/nginx/nginx.conf
COPY config/fpm-pool.conf /etc/php7/php-fpm.d/php_custom.conf
COPY config/php.ini /etc/php7/conf.d/php_custom.ini
COPY config/supervisord.conf /etc/supervisord.conf
COPY config/entrypoint.sh /entrypoint.sh

WORKDIR /var/www/html

ENTRYPOINT ["/entrypoint.sh"]

EXPOSE 80 443

CMD ["tail", "-f", "/var/log/lastlog"]
