FROM alpine:3.9 as buildbase

# Environments
# Set the lang, you can also specify it as as environment variable through docker-compose.yml
ENV LANG=en_US.UTF-8 
ENV LANGUAGE=en_US.UTF-8
ENV LC_ALL en_US.UTF-8
ENV TZ America/Sao_Paulo

# ENV LANG pt_BR.UTF-8
# ENV LANGUAGE pt_BR.UTF-8
# ENV LC_ALL pt_BR.UTF-8

RUN set -x \
    && apk update \
    && apk upgrade \
    && apk add --update --no-cache \
    tzdata \
    alpine-sdk \
    sudo \
    git \
    bash \
    && cp /usr/share/zoneinfo/${TZ} /etc/localtime \
    && echo "${TZ}" > /etc/timezone \
    # Cleaning up
    && apk del tzdata  \
    && rm -rf /usr/share/zoneinfo/Africa \
    && rm -rf /usr/share/zoneinfo/Antarctica  \
    && rm -rf /usr/share/zoneinfo/Arctic  \
    && rm -rf /usr/share/zoneinfo/Asia  \
    && rm -rf /usr/share/zoneinfo/Atlantic  \
    && rm -rf /usr/share/zoneinfo/Australia  \
    && rm -rf /usr/share/zoneinfo/Europe   \
    && rm -rf /usr/share/zoneinfo/Indian  \
    && rm -rf /usr/share/zoneinfo/Mexico  \
    && rm -rf /usr/share/zoneinfo/Pacific  \
    && rm -rf /usr/share/zoneinfo/Chile  \
    && rm -rf /usr/share/zoneinfo/Canada \   
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

# Iterate through all locale and install it
# Note that locale -a is not available in alpine linux, use `/usr/glibc-compat/bin/locale -a` instead
# COPY ./locale/locale.md /locale.md
# RUN cat locale.md | xargs -i /usr/glibc-compat/bin/localedef -i {} -f UTF-8 {}.UTF-8

