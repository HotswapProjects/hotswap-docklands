FROM hotswapagent/hotswap-vm
MAINTAINER hotswapagent.org
ENV PAYARA_ARCHIVE payaramicro41
ENV INSTALL_DIR /opt
RUN curl -o ${INSTALL_DIR}/${PAYARA_ARCHIVE}.jar -L "https://search.maven.org/remotecontent?filepath=fish/payara/extras/payara-micro/5.181/payara-micro-5.181.jar"
ENV PAYARA_HOME ${INSTALL_DIR}
ENV DEPLOYMENT_DIR ${PAYARA_HOME}
ENTRYPOINT java -jar ${PAYARA_ARCHIVE}.jar --deploy ${ARCHIVE_NAME}
WORKDIR ${INSTALL_DIR}
EXPOSE 8080 5900
