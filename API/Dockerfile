FROM bplus/buildbase:1.0.0 as api

RUN set -x \
    && apk update \
    && apk upgrade \
    && apk add --update --no-cache \
    tzdata \
    alpine-sdk \
    sudo \
    git \
    bash \
    && cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime \
    && echo "${TIMEZONE}" > /etc/timezone \
    # Cleaning up
    && apk del tzdata  \
    && rm -rf /var/cache/apk/*
