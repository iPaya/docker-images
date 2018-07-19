FROM ipaya/alpine:3.7

LABEL maintainer="zhangdi_me@163.com"

ENV PHP_VERSION="php7.1"

ENV \
    COMPOSER_ALLOW_SUPERUSER=1 \
    DEPS="${PHP_VERSION} \
        ${PHP_VERSION}-common \
        ${PHP_VERSION}-phar \
        ${PHP_VERSION}-bcmath \
        ${PHP_VERSION}-calendar \
        ${PHP_VERSION}-mbstring \
        ${PHP_VERSION}-exif \
        ${PHP_VERSION}-ftp \
        ${PHP_VERSION}-openssl \
        ${PHP_VERSION}-zip \
        ${PHP_VERSION}-sysvsem \
        ${PHP_VERSION}-sysvshm \
        ${PHP_VERSION}-sysvmsg \
        ${PHP_VERSION}-shmop \
        ${PHP_VERSION}-sockets \
        ${PHP_VERSION}-zlib \
        ${PHP_VERSION}-bz2 \
        ${PHP_VERSION}-curl \
        ${PHP_VERSION}-simplexml \
        ${PHP_VERSION}-xml \
        ${PHP_VERSION}-opcache \
        ${PHP_VERSION}-dom \
        ${PHP_VERSION}-xmlreader \
        ${PHP_VERSION}-xmlwriter \
        ${PHP_VERSION}-tokenizer \
        ${PHP_VERSION}-ctype \
        ${PHP_VERSION}-session \
        ${PHP_VERSION}-fileinfo \
        ${PHP_VERSION}-iconv \
        ${PHP_VERSION}-json \
        ${PHP_VERSION}-posix \
        ${PHP_VERSION}-intl \
        ${PHP_VERSION}-gd \
        ${PHP_VERSION}-mcrypt \
        ${PHP_VERSION}-pdo \
        ${PHP_VERSION}-pdo_mysql \
        ${PHP_VERSION}-mysqli \
        curl \
        ca-certificates \
        icu-libs \
        composer"

# 添加 PHP 源
ADD https://repos.php.earth/alpine/phpearth.rsa.pub /etc/apk/keys/phpearth.rsa.pub

# 安装 PHP
RUN set -x \
    && echo "https://repos.php.earth/alpine/v3.7" >> /etc/apk/repositories \
    && apk --no-cache add $DEPS

CMD ["php", "-a"]