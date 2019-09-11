FROM adoptopenjdk/openjdk8:jdk8u192-b12-alpine

COPY files/product/wso2am-2.6.0 /opt/wso2/wso2am-2.6.0
COPY files/product/api-import-export-2.6.0-v10.war /opt/wso2/wso2am-2.6.0/repository/deployment/server/webapps

WORKDIR /opt/wso2/wso2am-2.6.0
ENTRYPOINT ["bin/wso2server.sh"]
