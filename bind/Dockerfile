FROM alpine:latest
LABEL maintainer="Wataru Ohgai <alt@sfc.wide.ad.jp>"
LABEL version="1.0"
LABEL description="BIND"

RUN apk --update --no-cache add bind drill
RUN rm -rf /var/cache/apk/*
COPY ./named.conf /etc/bind/named.conf
RUN chown -R named:named /etc/bind
RUN chmod -R 755 /etc/bind

EXPOSE 53/udp
EXPOSE 53/tcp

ENTRYPOINT named -u named -g

