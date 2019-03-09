FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="OpenLiberty Kernel Development Builds"
ENV RELEASE 2019-02-22_1311
ENV VERSION 19.0.0.2
ENV INSTALL_DIR /opt/

# Download OpenLiberty
ENV OPENLIBERTY_HOME ${INSTALL_DIR}/openliberty-${VERSION}
ENV DEPLOYMENT_DIR ${OPENLIBERTY_HOME}/standalone/deployments/
RUN curl -O https://public.dhe.ibm.com/ibmdl/export/pub/software/openliberty/runtime/release/${RELEASE}/openliberty-${VERSION}.zip \
    && unzip openliberty-${VERSION}.zip -d ${INSTALL_DIR} \
    && rm openliberty-${VERSION}.zip
ENV CONFIG /opt/wlp/usr/servers/defaultServer/
EXPOSE 9080 9443
ENTRYPOINT /opt/wlp/bin/server run defaultServer
