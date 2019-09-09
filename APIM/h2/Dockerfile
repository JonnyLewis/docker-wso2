FROM adoptopenjdk/openjdk8:jdk8u192-b12-alpine

RUN  apk add --update --no-cache \
     curl \
     tzdata \
     netcat-openbsd && \
     rm -rf /var/cache/apk/*

COPY  files/product/wso2am-2.6.0 /opt/wso2/wso2am-2.6.0
WORKDIR /opt/wso2/wso2am-2.6.0
ENTRYPOINT ["bin/wso2server.sh"]