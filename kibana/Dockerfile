ARG ELK_VERSION

# https://www.docker.elastic.co/
#FROM docker.elastic.co/kibana/kibana:${ELK_VERSION}
FROM docker.elastic.co/kibana/kibana:${ELK_VERSION}

RUN kibana-plugin install https://github.com/bitsensor/elastalert-kibana-plugin/releases/download/1.1.0/elastalert-kibana-plugin-1.1.0-7.5.0.zip 

# Add your kibana plugins setup here
# Example: RUN kibana-plugin install <name|url>
