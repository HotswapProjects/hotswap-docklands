FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="OpenLiberty Kernel"

ENV LIBERTY_VERSION 19.0.0.2
ENV INSTALL_DIR /opt/ibm

# Download OpenLiberty
ENV OPENLIBERTY_HOME ${INSTALL_DIR}/openliberty-${LIBERTY_VERSION}
ENV DEPLOYMENT_DIR ${OPENLIBERTY_HOME}/standalone/deployments/
RUN curl -O https://repo1.maven.org/maven2/io/openliberty/openliberty-runtime/${LIBERTY_VERSION}/openliberty-runtime-${LIBERTY_VERSION}.zip \
    && unzip openliberty-runtime-${LIBERTY_VERSION}.zip -d ${INSTALL_DIR} \
    && rm openliberty-runtime-${LIBERTY_VERSION}.zip
ENV PATH=/opt/ibm/wlp/bin:$PATH

# Set Path Shortcuts
ENV LOG_DIR=/logs \
    WLP_OUTPUT_DIR=/opt/ibm/wlp/output

RUN mkdir /logs \
    && ln -s $WLP_OUTPUT_DIR/defaultServer /output \
    && ln -s /opt/ibm/wlp/usr/servers/defaultServer /config

# Configure WebSphere Liberty
RUN /opt/ibm/wlp/bin/server create \
    && rm -rf $WLP_OUTPUT_DIR/.classCache /output/workarea
COPY docker-server /opt/ibm/docker/
RUN chmod a+x /opt/ibm/docker/docker-server

EXPOSE 9080 9443

CMD ["/opt/ibm/docker/docker-server", "run", "defaultServer"]
