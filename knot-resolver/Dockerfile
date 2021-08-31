FROM alpine:latest
LABEL maintainer="Wataru Ohgai <alt@sfc.wide.ad.jp>"
LABEL version="1.0"
LABEL description="Knot Resolver"

RUN apk --update --no-cache add knot-resolver drill
RUN rm -rf /var/cache/apk/*
RUN rm /etc/knot-resolver/kresd.conf
COPY ./kresd.conf /etc/knot-resolver/kresd.conf
RUN chown -R kresd:kresd /etc/knot-resolver
RUN chmod -R 755 /etc/knot-resolver

EXPOSE 53/udp
EXPOSE 53/tcp

ENTRYPOINT kresd -c /etc/knot-resolver/kresd.conf -n -v

