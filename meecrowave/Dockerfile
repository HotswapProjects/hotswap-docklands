FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="Meecrowave"
ENV MEECROWAVE_ARCHIVE meecrowave-core-1.2.4-runner
ENV INSTALL_DIR /opt
RUN curl -o ${INSTALL_DIR}/${MEECROWAVE_ARCHIVE}.jar -L http://repo.maven.apache.org/maven2/org/apache/meecrowave/meecrowave-core/1.2.4/meecrowave-core-1.2.4-runner.jar
ENV MEECROWAVE_HOME ${INSTALL_DIR}
ENV DEPLOYMENT_DIR ${MEECROWAVE_HOME}
ENTRYPOINT java ${JAVA_OPTS} -jar ${MEECROWAVE_ARCHIVE}.jar --webapp ${ARCHIVE_NAME} --context ${CONTEXT}
WORKDIR ${INSTALL_DIR}
EXPOSE 8080 8000
