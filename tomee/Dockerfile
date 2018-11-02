FROM hotswapagent/hotswap-vm
LABEL maintainer="hotswapagent.org" description="TomEE Plus"
ENV ARCHIVE apache-tomee-plus-7.0.4
ENV INSTALL_DIR /opt
ENV SERVER_HOME ${INSTALL_DIR}/${ARCHIVE}
ENV DEPLOYMENT_DIR ${SERVER_HOME}/webapps/
# ENV JAVA_OPTS="-XXaltjvm=dcevm -agentlib:jdwp=transport=dt_socket,server=y,address=8000,suspend=n -javaagent:/opt/hotswap-agent/hotswap-agent.jar"
RUN apk -U upgrade \
    && apk add curl \
    && curl -o ${SERVER_HOME}.zip -L http://repo.maven.apache.org/maven2/org/apache/tomee/apache-tomee/7.0.5/apache-tomee-7.0.5-plus.zip \
    && unzip ${SERVER_HOME}.zip -d /opt \
    && rm ${SERVER_HOME}.zip \
    && ln -s ${DEPLOYMENT_DIR} /deployment_dir
ENTRYPOINT ${SERVER_HOME}/bin/catalina.sh run
EXPOSE 8080 8000
