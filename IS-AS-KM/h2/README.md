# IS-AS-KM Docker Container H2 (Default)

## Pre-Requisites
To build the docker image you must have the **WSO2 IS as KM** product downloaded and extraced under **/files/product** directory.

**Note:** It's not necessary to extract the product zip. You can even use commands to extract the zip file. For the sake of simplicity I have extracted the product zip and in the Dockerfile I copy the extracted zip to the image.

## Remove Image if exists
```
docker image rm anupamgogoi/is-as-km-570
```

## Create Image
```
docker build -t anupamgogoi/is-as-km-570 .
```

## Run Image
```
docker run -d -t --name is-as-km-570 \
-p 9443:9443 \
anupamgogoi/is-as-km-570
```
