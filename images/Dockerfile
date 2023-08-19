FROM alpine:3.18
RUN apk add --no-cache openrc sudo
RUN wget -O - thin-edge.io/install.sh | sh -s
RUN wget -O - thin-edge.io/install-services.sh | sh -s

COPY ./images/files/bootstrap.sh /usr/bin/
COPY ./dist/*.apk /tmp/
RUN apk add --allow-untrusted /tmp/tedge-apk-plugin*.apk

ENTRYPOINT ["/sbin/init"]