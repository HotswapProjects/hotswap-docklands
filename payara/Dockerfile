FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="Payara Server Full"
ENV PAYARA_ARCHIVE payara41
ENV DOMAIN_NAME domain1
ENV INSTALL_DIR /opt
RUN adduser -D -s /bin/sh -h ${INSTALL_DIR} serveradmin && echo serveradmin:serveradmin | chpasswd
RUN curl -o ${INSTALL_DIR}/${PAYARA_ARCHIVE}.zip -L https://s3-eu-west-1.amazonaws.com/payara.fish/Payara+Downloads/Payara+4.1.2.181/payara-4.1.2.181.zip \ 
    && unzip ${INSTALL_DIR}/${PAYARA_ARCHIVE}.zip -d ${INSTALL_DIR} \ 
    && rm ${INSTALL_DIR}/${PAYARA_ARCHIVE}.zip \
    && chown -R serveradmin:serveradmin /opt \
    && chmod -R a+rw /opt

ENV PAYARA_HOME ${INSTALL_DIR}/payara41/glassfish
ENV DEPLOYMENT_DIR ${INSTALL_DIR}/deploy
RUN mkdir ${DEPLOYMENT_DIR}
WORKDIR ${PAYARA_HOME}/bin
ADD start.sh .
RUN chmod a+x start.sh
RUN cp /opt/hotswap-agent/hotswap-agent.jar ${PAYARA_HOME}//domains/domain1/lib/ext/
ENTRYPOINT start.sh
USER serveradmin
EXPOSE 4848 8009 8080 8181
