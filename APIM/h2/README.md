# APIM Docker Container With H2 (Default)

## Pre-Requisites
To build the docker image you must have the **WSO2 API Manager** product downloaded and extraced under **/files/product** directory.

**Note**: It's not necessary to extract the product zip. You can even use commands to extract the zip file. For the sake of simplicity I have extracted the product zip and in the Dockerfile I copy the extracted zip to the image.

## Remove APIM Image if exists
```
docker image rm anupamgogoi/wso2am-260
```

## Create APIM Image
```
docker build -t anupamgogoi/wso2am-260 .
```

## Run APIM Image
```
docker run -d -t --name wso2am-260 -p 9443:9443 -p 9763:9763 -p 8243:8243 -p 8280:8280 -p 10397:10397 -p 7711:7711 anupamgogoi/wso2am-260

```
