
# APIM Docker Container With MySQL Configuration

## Remove Image if exists
```
docker image rm anupamgogoi/wso2am-260-mysql
```

## Create Image
In the [Dockerfile](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/Dockerfile), we explicitely configure the MySQL
```
docker build -t anupamgogoi/wso2am-260-mysql .
```

## Run Image

```
docker run -d -t --name wso2 \
-p 9443:9443 -p 9763:9763 \
-p 8243:8243 -p 8280:8280 \
-p 10397:10397 \
-p 7711:7711 \
anupamgogoi/wso2am-260-mysql
```

# Docker Compose

## Docker Container With MySQL
In the [docker-compose-1.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/docker-compose-1.yml), we explictely use the docker image of APIM that was configured for MySQL.
```
docker-compose -f docker-compose-1.yml up
```

## Docker Container Without MySQL
In the [docker-compose-2.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/docker-compose-2.yml), we use the APIM docker image that was configured to use the default database (H2). Then we explitely map volumes to use MySQL configurations.
```
docker-compose -f docker-compose-2.yml up
```
