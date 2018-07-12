FROM ipaya/php:7.0

LABEL maintainer="zhangdi_me@163.com"

ENV \
    PHP_MEMORY_LIMIT="256M" \
    PHP_UPLOAD_MAX_FILESIZE="20M" \
    PHP_MAX_FILE_UPLOADS="100" \
    PHP_POST_MAX_SIZE="50M" \
    DEPS="${PHP_VERSION}-fpm"

# 安装依赖
RUN set -x \
    && apk --no-cache add $DEPS

# 配置
RUN set -x \
    && sed -i -e "s|;daemonize\s*=\s*yes|daemonize = no|g" /etc/php/7.0/php-fpm.conf \
    && sed -i -e "s|listen\s*=\s*/run/php-fpm7.0/php-fpm.sock|listen = /run/php-fpm7.0/php-fpm.sock\nlisten = 9000\n|g" /etc/php/7.0/php-fpm.d/www.conf \
    && sed -i "s|memory_limit =.*|memory_limit = ${PHP_MEMORY_LIMIT}|" /etc/php/7.0/php.ini \
    && sed -i "s|upload_max_filesize =.*|upload_max_filesize = ${PHP_UPLOAD_MAX_FILESIZE}|" /etc/php/7.0/php.ini \
    && sed -i "s|max_file_uploads =.*|max_file_uploads = ${PHP_MAX_FILE_UPLOADS}|" /etc/php/7.0/php.ini \
    && sed -i "s|post_max_size =.*|post_max_size = ${PHP_POST_MAX_SIZE}|" /etc/php/7.0/php.ini \
    && sed -i "s|;cgi.fix_pathinfo=1|cgi.fix_pathinfo=0|" /etc/php/7.0/php.ini

CMD ["php-fpm"]
EXPOSE 9000