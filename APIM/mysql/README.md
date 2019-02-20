
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

# Docker File (MySQL Container + APIM Container With MySQL Config)
![](https://github.com/anupamgogoi-wso2/docker-wso2/blob/master/APIM/mysql/files/product/access-mysql-container-from-another-container.jpg?raw=true)

Here is a sample configuration of datasource in master-datasources.xml,
```
<?xml version="1.0" encoding="UTF-8"?>
<datasource>
   <name>WSO2UM_DB</name>
   <description>The datasource used by user manager</description>
   <jndiConfig>
      <name>jdbc/WSO2UM_DB</name>
   </jndiConfig>
   <definition type="RDBMS">
      <configuration>
         <!-- Use IP of the machine -->
         <url>jdbc:mysql://192.168.43.63:3306/userdb?useSSL=false</url>
         <username>root</username>
         <password>root</password>
         <driverClassName>com.mysql.jdbc.Driver</driverClassName>
         <maxActive>80</maxActive>
         <maxWait>60000</maxWait>
         <minIdle>5</minIdle>
         <testOnBorrow>true</testOnBorrow>
         <validationQuery>SELECT 1</validationQuery>
         <validationInterval>30000</validationInterval>
         <defaultAutoCommit>true</defaultAutoCommit>
      </configuration>
   </definition>
</datasource>
```
