
# Pre-Requisites
To build the docker image you must have the **WSO2 API Manager** product downloaded and extraced under **/files/product** directory.

**Note:** It's not necessary to extract the product zip. You can even use commands to extract the zip file. For the sake of simplicity I have extracted the product zip and in the Dockerfile I copy the extracted zip to the image.

# Docker Compose (MySQL + APIM)

Here, we make composition of two docker images,

1. MySQL
2. anupamgogoi/wso2am-260

In the [docker-compose-2.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/docker-compose-2.yml), we use the APIM docker image that was configured to use the default database (H2). Then we explitely map volumes to use MySQL configurations.
```
docker-compose -f docker-compose-2.yml up
```
