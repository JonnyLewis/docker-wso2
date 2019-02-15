
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
