# Docker Container With H2 (Default)

## Remove Image if exists
```
docker image rm anupamgogoi/wso2am-260
```

## Create Image
```
docker build -t anupamgogoi/wso2am-260 .
```

## Run Image
```
docker run -d -t --name wso2am-260 
-p 9443:9443 \
-p 9763:9763 \
-p 8243:8243 \
-p 8280:8280 \
-p 10397:10397 \ 
-p 7711:7711 \
anupamgogoi/wso2am-260
```
