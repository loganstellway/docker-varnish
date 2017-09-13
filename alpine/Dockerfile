FROM alpine:3.6

# Environment
ENV VARNISH_BACKEND_HOST localhost
ENV VARNISH_BACKEND_PORT 80
ENV VARNISH_THREAD_POOLS 25
ENV VARNISH_THREAD_POOL_MIN 100
ENV VARNISH_CLI_TIMEOUT 86400
ENV VARNISH_STORAGE 1G
ENV VARNISH_SECRET=

# Install Varnish
RUN set -ex \
      && apk add --update \
        bash \
        varnish \
      && rm -rf /var/cache/apk/*

WORKDIR /etc/varnish

COPY varnish-init /usr/local/bin/

EXPOSE 80
EXPOSE 6082

CMD ["varnish-init"]
