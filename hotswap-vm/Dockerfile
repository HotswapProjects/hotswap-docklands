FROM anapsix/alpine-java:8_jdk-dcevm
LABEL maintainer="hotswapagent.org" description="DCEVM+HotswapAgent"
RUN apk -U upgrade \
    && apk add curl \
    && apk add unzip \
    && mkdir -p /opt/hotswap-agent/ \
    && curl -L -o /opt/hotswap-agent/hotswap-agent-1.3.1-SNAPSHOT.jar "https://github.com/HotswapProjects/HotswapAgent/releases/download/1.3.1-SNAPSHOT/hotswap-agent-1.3.1-SNAPSHOT.jar" \
    && ln -f -s /opt/hotswap-agent/hotswap-agent-1.3.1-SNAPSHOT.jar /opt/hotswap-agent/hotswap-agent.jar
