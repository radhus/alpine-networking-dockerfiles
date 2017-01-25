FROM alpine:3.5

ENV OPENVPN_VER 2.3.14-r0

RUN apk add --no-cache \
      openvpn==${OPENVPN_VER}

ENTRYPOINT /usr/sbin/openvpn
