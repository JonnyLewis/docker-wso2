FROM adoptopenjdk/openjdk8:jdk8u192-b12-alpine
MAINTAINER agogoi@wso2.com

# Variables
ARG USER=wso2carbon
ARG USER_ID=802
ARG USER_GROUP=wso2
ARG USER_GROUP_ID=802
ARG USER_HOME=/home/${USER}

# Create group and add user wso2
RUN  addgroup -g ${USER_GROUP_ID} ${USER_GROUP}
RUN  adduser -u ${USER_ID} -D -g '' -h ${USER_HOME} -G ${USER_GROUP} ${USER}


# Copy the necessary product zip.
COPY files/product/wso2am-2.6.0 /home/wso2carbon/wso2am-2.6.0

# Give permission to the user. (user:group)
RUN chown -R wso2carbon:wso2 /home/wso2carbon/wso2am-2.6.0

# Switch to user wso2carbon.
USER wso2carbon

# Set working directory
WORKDIR /home/wso2carbon/wso2am-2.6.0

# Expose ports
EXPOSE 8280 8243 9763 9443 9099 5672 9711 9611 7711 7611 10397

ENTRYPOINT ["bin/wso2server.sh"]
