FROM java:8
RUN apt-get update

# Usually the product is downloaded from site. For simplicity I am using an already downloaded copy
COPY files/product/wso2am-2.6.0 /opt/wso2/wso2am-2.6.0

# Copy the configs.
COPY files/apim/api-manager.xml /opt/wso2/wso2am-2.6.0/repository/conf/api-manager.xml
COPY files/apim/registry.xml /opt/wso2/wso2am-2.6.0/repository/conf/registry.xml
COPY files/apim/user-mgt.xml /opt/wso2/wso2am-2.6.0/repository/conf/user-mgt.xml

# Copy datasource configs.
COPY files/apim/datasources/master-datasources-without-docker-compose.xml /opt/wso2/wso2am-2.6.0/repository/conf/datasources/master-datasources.xml

# Copy mysql-driver
COPY files/lib/mysql-connector-java-8.0.12.jar /opt/wso2/wso2am-2.6.0/repository/components/lib/mysql-connector-java-8.0.12.jar

WORKDIR /opt/wso2/wso2am-2.6.0
ENTRYPOINT ["bin/wso2server.sh"]