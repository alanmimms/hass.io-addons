ARG BUILD_FROM=hassioaddons/base-aarch64
FROM ${BUILD_FROM}

# Add env
ENV LANG C.UTF-8

# Copy root filesystem
COPY rootfs /

# Setup base
RUN apk add --no-cache \
    python3 \
    jq \
    py-pip \
    python \
    python-dev \
    python3 \
    python3-dev \
&& pip install -U pip \
&& pip3 install -U pip \
&& pip3 install rpi-rf

# Scrip to run after startup
CMD [ "/usr/bin/run.sh" ]

# Build arugments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="RPI-RF" \
    io.hass.description="433MHz RF for Raspberry Pi add-on by Alan Mimms Hass.io Add-ons" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Alan MImms <alanmimms@gmail.com>" \
    org.label-schema.description="433MHz RF for Raspberry Pi add-on by Alan Mimms Hass.io Add-ons" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="RPI-RF" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.url="https://addons.community" \
    org.label-schema.usage="https://github.com/alanmimms/hass.io-addons/tree/master/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/alanmimms/hass.io-addons" \
    org.label-schema.vendor="Alan Mimms Hass.io Addons"
