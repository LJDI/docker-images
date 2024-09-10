
FROM python:3-alpine

ARG VERSION

RUN wget -O /XX-Net.zip https://github.com/XX-net/XX-Net/releases/download/${VERSION}/XX-Net-linux-${VERSION}.zip \
    && unzip XX-Net-linux-5.10.7.zip -x "XX-Net/python3/*" "XX-Net/SwitchyOmega/*" \
    && apk --no-cache add iproute2 \
    && rm -r /root/XX-Net.zip /root/XX-Net/python*

WORKDIR /XX-Net


EXPOSE 8085 8086 8087 1080
CMD ["/bin/sh","-c", "./start -allow_remote"]
