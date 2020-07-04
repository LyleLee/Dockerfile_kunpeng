FROM golang:1.14-alpine

WORKDIR /go/src/app
RUN cp -a /etc/apk/repositories /etc/apk/repositories.bak && \
    sed -i "s@http://dl-cdn.alpinelinux.org/@https://mirrors.huaweicloud.com/@g" /etc/apk/repositories
RUN apk update && apk add libpcap-dev && apk add git && apk add gcc && apk add g++ && apk add openssh-client

VOLUME /go/src/app


CMD ["/bin/sh"]

