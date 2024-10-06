FROM alpine

ARG BASE_DOWNLOAD_URL="https://github.com/fatedier/frp/releases/download"

ARG VERSION
ARG TARGETPLATFORM

ARG HTTP_PROXY
ARG HTTPS_PROXY
ARG ALL_PROXY
ARG NO_PROXY

RUN case "${TARGETPLATFORM}" in \
      "amd64") DOWNLOAD_URL="${BASE_DOWNLOAD_URL}/v${VERSION}/frp_${VERSION}_linux_amd64.tar.gz" ;; \
      "arm")   DOWNLOAD_URL="${BASE_DOWNLOAD_URL}/v${VERSION}/frp_${VERSION}_linux_arm.tar.gz" ;; \
      "armhf") DOWNLOAD_URL="${BASE_DOWNLOAD_URL}/v${VERSION}/frp_${VERSION}_linux_armhf.tar.gz" ;; \
      "arm64") DOWNLOAD_URL="${BASE_DOWNLOAD_URL}/v${VERSION}/frp_${VERSION}_linux_arm64.tar.gz" ;; \
    *)               echo "Unsupported platform: ${TARGETPLATFORM}" && exit 1 ;; \
    esac && \
    echo "Downloading from ${DOWNLOAD_URL}" && \
    mkdir /etc/frp && \
    wget "${DOWNLOAD_URL}" -O - | tar -zxf - --strip-components=1 -C /etc/frp && \
    mv /etc/frp/frpc /usr/local/bin && \
    mv /etc/frp/frps /usr/local/bin && \
    echo "Frp installed"

VOLUME ["/etc/frp"]


