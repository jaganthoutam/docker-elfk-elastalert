FROM mmguero/elastalert:2.0.2

USER root

RUN apk update && \
    apk add bash curl && \
    rm -rf /var/cache/apk/*


ADD elastalert/elastalert/elastalert-start.sh /usr/local/bin/
ADD elastalert/shared/bin/elastic_search_status.sh /usr/local/bin/

RUN chmod +x /usr/local/bin/elastalert-start.sh && \
    mkdir -p /opt/elastalert/server_data/tests && \
    chown -R node:node /opt

VOLUME ["/opt/elastalert/server_data"]

USER node

ENTRYPOINT ["/usr/local/bin/elastalert-start.sh"]


# to be populated at build-time:
ARG BUILD_DATE
ARG MALCOLM_VERSION
ARG VCS_REVISION
