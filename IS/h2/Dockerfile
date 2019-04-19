FROM java:8

COPY  files/product/wso2is-5.7.0 /opt/wso2/wso2is-5.7.0

# Just copy the jar and do nothing else.
COPY files/lib/mysql-connector-java-8.0.12.jar /opt/wso2/wso2is-5.7.0/repository/components/lib/mysql-connector-java-8.0.12.jar

WORKDIR /opt/wso2/wso2is-5.7.0
ENTRYPOINT ["bin/wso2server.sh"]