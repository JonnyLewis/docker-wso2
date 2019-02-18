
# Pre-Requisites
To build the docker image you must have the **WSO2 API Manager** and **WSO2 API Manager** product downloaded and extraced under **/files/product** directory.

**Note:** It's not necessary to extract the product zip. You can even use commands to extract the zip file. For the sake of simplicity I have extracted the product zip and in the Dockerfile I copy the extracted zip to the image.

# Docker Compose (MySQL + APIM + IS-AS-KM)

Here, we make composition of three docker images,

1. MySQL
2. anupamgogoi/wso2am-260
3. anupamgogoi/is-as-km-570

In the [docker-compose.yml](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM-WITH-IS-AS-KM/mysql/docker-compose.yml), we first configure MySQL to create the necessary databases and scripts. 

Then in the APIM and IS-AS-KM images we configure volume mappings to put necessary configurations from local machine to contaner. 

```
docker-compose -f docker-compose.yml up
```
