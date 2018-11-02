FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="Wildfly hollow swarm"
ENV HOLLOWSWARM_ARCHIVE microprofile-2018.3.3-hollowswarm.jar
ENV INSTALL_DIR /opt
RUN curl -o ${INSTALL_DIR}/${HOLLOWSWARM_ARCHIVE}.jar -L http://repo2.maven.org/maven2/org/wildfly/swarm/servers/microprofile/2018.5.0/microprofile-2018.5.0-hollowswarm.jar
ENV HOLLOWSWARM_HOME ${INSTALL_DIR}
ENV DEPLOYMENT_DIR ${HOLLOWSWARM_HOME}
ENTRYPOINT java ${JAVA_OPTS} -jar ${HOLLOWSWARM_ARCHIVE}.jar ${ARCHIVE_NAME} -b=0.0.0.0
WORKDIR ${INSTALL_DIR}
EXPOSE 8080 9990
