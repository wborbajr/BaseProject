FROM bplus/buildbase:1.0.0 as database

ENV TERM=linux
ENV MONGODB_VERSION=3.2.10-r1

RUN set -x \
    && apk update  \
    && apk add mongodb --update-cache --repository http://dl-4.alpinelinux.org/alpine/edge/testing --allow-untrusted  \
    # Cleaning up
    && rm -rf /var/cache/apk/*

RUN mkdir -p /data/db \
    && chown -R mongodb /data/db

VOLUME /data/db

EXPOSE 27017

CMD [ "mongod", "--bind_ip", "0.0.0.0"]