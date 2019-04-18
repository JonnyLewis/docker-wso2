FROM centos:7
MAINTAINER agogoi@wso2.com

# Create group and add user wso2
RUN groupadd admin
RUN useradd -g admin wso2


# Copy the necessary product zip.
COPY files/product/jdk1.8.0_201 /home/wso2/jdk1.8.0_201
COPY files/product/wso2am-2.6.0 /home/wso2/wso2am-2.6.0
COPY files/lib/mysql-connector-java-8.0.12.jar /home/wso2/wso2am-2.6.0/repository/components/lib/mysql-connector-java-8.0.12.jar

# Copy config file/s.
COPY files/apim/axis2.xml /home/wso2/wso2am-2.6.0/repository/conf/axis2/axis2.xml

# Give permission to the user.
RUN chown -R wso2:admin /home/wso2

# Switch to user wso2.
USER wso2

# Set environment variables.
ENV JAVA_HOME=/home/wso2/jdk1.8.0_201

# Set working directory
WORKDIR /home/wso2/wso2am-2.6.0

# Expose ports
EXPOSE 8280 8243 9763 9443 9099 5672 9711 9611 7711 7611 10397

ENTRYPOINT ["bin/wso2server.sh"]
