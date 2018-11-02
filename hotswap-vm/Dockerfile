FROM anapsix/alpine-java:8_jdk-dcevm
LABEL maintainer="hotswapagent.org" description="DCEVM+HotswapAgent"
RUN apk -U upgrade \
    && apk add curl \
    && apk add unzip \
    && mkdir -p /opt/hotswap-agent/ \
    && curl -L -o /opt/hotswap-agent/hotswap-agent-1.3.0.jar "https://github.com/HotswapProjects/HotswapAgent/releases/download/RELEASE-1.3.0/hotswap-agent-1.3.0.jar" \
    && ln -s /opt/hotswap-agent/hotswap-agent-1.3.0.jar /opt/hotswap-agent/hotswap-agent.jar
