ARG ELK_VERSION

FROM docker.elastic.co/beats/filebeat:${ELK_VERSION}
 
USER root
RUN chown -R root /usr/share/filebeat/
RUN chmod -R go-w /usr/share/filebeat/
