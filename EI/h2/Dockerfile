FROM java:8
RUN apt-get update

COPY  files/product/wso2ei-6.3.0 /opt/wso2/wso2ei
WORKDIR /opt/wso2/wso2ei-6.3.0
ENTRYPOINT ["bin/integrator.sh"]