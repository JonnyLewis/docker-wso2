FROM java:8
#RUN apt-get update

COPY  files/product/wso2am-2.6.0 /opt/wso2/wso2am-2.6.0
WORKDIR /opt/wso2/wso2am-2.6.0
ENTRYPOINT ["bin/wso2server.sh"]