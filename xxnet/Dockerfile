
FROM python:3-alpine

ARG HTTP_PROXY
ARG HTTPS_PROXY
ARG ALL_PROXY
ARG NO_PROXY

ARG VERSION

RUN apk --quiet --no-cache add wget iproute2 \
    && wget -qO /tmp/XX-Net.zip https://github.com/XX-net/XX-Net/releases/download/${VERSION}/XX-Net-linux-${VERSION}.zip \
    && unzip -q /tmp/XX-Net.zip -x "XX-Net/python3/*" "XX-Net/SwitchyOmega/*" \
    && rm /tmp/XX-Net.zip


EXPOSE 8085 8086 8087 1080
CMD ["/bin/sh","-c", "/XX-Net/start -allow_remote"]
