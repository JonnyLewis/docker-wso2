FROM adoptopenjdk/openjdk8:jdk8u192-b12-alpine
MAINTAINER agogoi@wso2.com

# Variables
ARG USER=wso2carbon
ARG USER_ID=802
ARG USER_GROUP=wso2
ARG USER_GROUP_ID=802
ARG USER_HOME=/home/${USER}
ARG WSO2_SERVER_HOME=${USER_HOME}/wso2am-2.6.0


# Create group and add user wso2
RUN  addgroup -g ${USER_GROUP_ID} ${USER_GROUP}
RUN  adduser -u ${USER_ID} -D -g '' -h ${USER_HOME} -G ${USER_GROUP} ${USER}

# Default Java preference dirs.
RUN mkdir -p ${USER_HOME}/.java/.systemPrefs
RUN mkdir -p ${USER_HOME}/.java/.userPrefs
RUN chmod -R 755 ${USER_HOME}/.java
RUN chown -R ${USER}:${USER_GROUP} ${USER_HOME}/.java


# Copy the necessary product zip.
COPY files/product/wso2am-2.6.0 ${WSO2_SERVER_HOME}

# Give permission to the user. (user:group)
RUN chown -R wso2carbon:wso2 ${WSO2_SERVER_HOME}

# Switch to user wso2carbon.
USER ${USER_ID}

# Set working directory
WORKDIR ${WSO2_SERVER_HOME}

# Expose ports
EXPOSE 8280 8243 9763 9443 9099 5672 9711 9611 7711 7611 10397

ENTRYPOINT ["bin/wso2server.sh"]
