
# Docker Compose (MySQL + APIM)

Here, we make composition of two docker images,

1. MySQL
2. anupamgogoi/wso2am-260

In the [docker-compose-2.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/docker-compose-2.yml), we use the APIM docker image that was configured to use the default database (H2). Then we explitely map volumes to use MySQL configurations.
```
docker-compose -f docker-compose-2.yml up
```
