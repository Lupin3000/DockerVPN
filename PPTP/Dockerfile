FROM alpine

MAINTAINER lupin3000

RUN apk --update add pptpd \
    && rm -rf /var/cache/apk/*

COPY ["pptpd.conf", "/etc/"]
COPY ["chap-secrets", "options.pptp", "/etc/ppp/"]

EXPOSE 1723

CMD ["/bin/sh"]
