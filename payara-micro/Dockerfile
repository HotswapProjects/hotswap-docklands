FROM hotswapagent/hotswap-vm
MAINTAINER hotswapagent.org
ENV PAYARA_ARCHIVE payaramicro41
ENV INSTALL_DIR /opt
RUN curl -o ${INSTALL_DIR}/${PAYARA_ARCHIVE}.jar -L "https://search.maven.org/remotecontent?filepath=fish/payara/extras/payara-micro/5.191/payara-micro-5.191.jar"
ENV PAYARA_HOME ${INSTALL_DIR}
ENV DEPLOYMENT_DIR ${PAYARA_HOME}
ENTRYPOINT java ${JAVA_OPTS} -jar ${PAYARA_ARCHIVE}.jar --deploy ${ARCHIVE_NAME} ${DEPLOY_OPTS}
WORKDIR ${INSTALL_DIR}
EXPOSE 8080 5900
