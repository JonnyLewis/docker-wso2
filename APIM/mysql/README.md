
# Docker Container With MySQL Configuration

## Remove Image if exists
```
docker image rm anupamgogoi/wso2am-260-mysql
```

## Create Image
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
```
docker-compose -f docker-compose-1.yml up
```

## Docker Container Without MySQL
```
docker-compose -f docker-compose-2.yml up
```
