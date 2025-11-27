
ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:latest
ARG SNAPCAST_VERSION=0.31.0-r0

FROM $BUILD_FROM
ARG SNAPCAST_VERSION

# install snapcast
RUN apk add \
        snapcast-server=${SNAPCAST_VERSION} \
        avahi \
        dbus

RUN wget -O snapweb.zip https://github.com/badaix/snapweb/releases/download/v0.9.2/snapweb.zip \
    && rm -rf /usr/share/snapserver/snapweb \
    && mkdir -p /usr/share/snapserver/snapweb \
    && unzip snapweb.zip -d /usr/share/snapserver/snapweb \
    && rm snapweb.zip

# Copy root filesystem
COPY rootfs /
