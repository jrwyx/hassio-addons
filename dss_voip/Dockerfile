ARG BUILD_FROM=hassioaddons/base:6.0.1
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Environment variables
ENV \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=2 \
    S6_CMD_WAIT_FOR_SERVICES=1 \
    TERM="xterm-256color"

ENV LANG C.UTF-8

# Copy root filesystem
COPY rootfs /

# Setup base
RUN apk add --no-cache \
    coreutils=8.31-r0 \
    wget=1.20.3-r0 \
    sox \
    pjsua \
    screen
    
# Build arguments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="DSS VoIP Notifier (ModByJr)" \
    io.hass.description="VoIP Notifier for HomeAssistant (ModByJr)" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="SDeSalve <me@nomail.com>" \
    org.label-schema.description="VoIP Notifier for HomeAssistant (ModByJr)" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="Addon VoIP for ${BUILD_ARCH} (ModByJr)" \
    org.label-schema.schema-version="3.1.5.2" \
    org.label-schema.url="https://noweb.com" \
    org.label-schema.usage="https://github.com/jr_wyx/hassio-addons/dss_voip/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/jr_wyx/hassio-addons/dss_voip" \
    org.label-schema.vendor="SDeSalve (ModByJr)"
