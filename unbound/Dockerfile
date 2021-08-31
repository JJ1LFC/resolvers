FROM alpine:latest
LABEL maintainer="Wataru Ohgai <alt@sfc.wide.ad.jp>"
LABEL version="1.0"
LABEL description="Unbound"

RUN apk --update --no-cache add unbound drill
RUN rm -rf /var/cache/apk/*
RUN rm /etc/unbound/unbound.conf
COPY ./unbound.conf /etc/unbound/unbound.conf
RUN unbound-anchor -4 -a /etc/unbound/root.key || return 0
RUN chown -R unbound:unbound /etc/unbound
RUN chmod -R 755 /etc/unbound

EXPOSE 53/udp
EXPOSE 53/tcp

ENTRYPOINT unbound -d

