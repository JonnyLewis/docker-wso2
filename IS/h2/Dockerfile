FROM java:8
#RUN apt-get update

COPY  files/product/wso2is-5.7.0 /opt/wso2/wso2is-5.7.0
WORKDIR /opt/wso2/wso2is-5.7.0
ENTRYPOINT ["bin/wso2server.sh"]