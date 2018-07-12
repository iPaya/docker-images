FROM alpine:3.8

LABEL maintainer="zhangdi_me@163.com"

ENV TIMEZONE Asia/Shanghai

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.aliyun.com/g' /etc/apk/repositories \
    && apk add --no-cache tzdata \
    && cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
    && echo "${TIMEZONE}" > /etc/timezone \
    && apk del --no-cache tzdata