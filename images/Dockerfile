ARG TEST_IMAGE=alpine:3.18
FROM ${TEST_IMAGE}
RUN apk add --no-cache openrc sudo bash curl
RUN wget -O - thin-edge.io/install.sh | sh -s -- --init-system openrc \
    && mkdir -p /etc/tedge/mappers/local

COPY ./images/files/bootstrap.sh /usr/bin/
COPY ./dist/*.apk /tmp/
RUN apk add --allow-untrusted /tmp/tedge-apk-plugin*.apk

ENTRYPOINT ["/sbin/init"]