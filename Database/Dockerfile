FROM bplus/buildbase:1.0.0 as database

ENV TERM=linux
ENV MONGODB_VERSION=3.2.10-r1

RUN set -x \
    && apk update  \
    && apk add mongodb --update-cache --repository \
    http://dl-4.alpinelinux.org/alpine/edge/testing \
    --allow-untrusted  \
    # Cleaning up
    && rm -rf /var/cache/apk/* \
    && rm -rf /tmp/*

RUN mkdir -p /data/db \
    && chown -R mongodb /data/db

VOLUME /data/db

# Expose ports.
#   - 27017: process
#   - 28017: http
EXPOSE 27017
EXPOSE 28017

CMD ["mongod", "--bind_ip", "0.0.0.0"]