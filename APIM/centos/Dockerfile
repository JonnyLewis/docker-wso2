FROM centos:7
MAINTAINER agogoi@wso2.com

# Create group and add user wso2
RUN groupadd admin
RUN useradd -g admin wso2
RUN chown -R wso2:admin /home/wso2

# Copy the necessary files.
COPY --chown=wso2:admin files/product/jdk1.8.0_201 /home/wso2/jdk1.8.0_201
COPY --chown=wso2:admin files/product/wso2am-2.6.0 /home/wso2/wso2am-2.6.0

# Switch to user wso2.
USER wso2

# Set environment variables.
ENV JAVA_HOME=/home/wso2/jdk1.8.0_201
WORKDIR /home/wso2/wso2am-2.6.0
ENTRYPOINT ["bin/wso2server.sh"]
