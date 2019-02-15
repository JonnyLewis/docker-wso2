
# Docker Compose (MySQL + APIM + IS-AS-KM)

Here, we make composition of three docker images,

1. MySQL
2. anupamgogoi/wso2am-260
3. anupamgogoi/is-as-km-570

In the [docker-compose.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM-WITH-IS-AS-KM/mysql/docker-compose.yml), we use the APIM docker image that was configured to use the default database (H2). Then we explitely map volumes to use MySQL configurations.
```
docker-compose -f docker-compose-2.yml up
```
