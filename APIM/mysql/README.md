
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


For more information, read [this](https://docs.docker.com/network/network-tutorial-standalone/).

## Too Long, Didn't Read

Execute the following command to check the IP address of the MySQL container
```
docker inspect <ID or Name of Container>
```

Following is a part of the output,
```
"NetworkSettings": {
            "Bridge": "",
            "SandboxID": "909c1a2814f928d5f8e36692a01f5f52452f11688815b891212dd21071cdf5ff",
            "HairpinMode": false,
            "LinkLocalIPv6Address": "",
            "LinkLocalIPv6PrefixLen": 0,
            "Ports": {
                "3306/tcp": [
                    {
                        "HostIp": "0.0.0.0",
                        "HostPort": "3306"
                    }
                ],
                "33060/tcp": null
            },
            "SandboxKey": "/var/run/docker/netns/909c1a2814f9",
            "SecondaryIPAddresses": null,
            "SecondaryIPv6Addresses": null,
            "EndpointID": "af42aeb93bb79147b9ef31d01d715f2cec8f56ee98098eb0c4cb363438a6c6b2",
            "Gateway": "172.17.0.1",
            "GlobalIPv6Address": "",
            "GlobalIPv6PrefixLen": 0,
            "IPAddress": "172.17.0.2",
            "IPPrefixLen": 16,
            "IPv6Gateway": "",
            "MacAddress": "02:42:ac:11:00:02",
            "Networks": {
                "bridge": {
                    "IPAMConfig": null,
                    "Links": null,
                    "Aliases": null,
                    "NetworkID": "c25e17ca3f3d831675d1dcbd8ee9ab4f0cbbfd2d3f90f1e9df6feb4284c4b030",
                    "EndpointID": "af42aeb93bb79147b9ef31d01d715f2cec8f56ee98098eb0c4cb363438a6c6b2",
                    "Gateway": "172.17.0.1",
                    "IPAddress": "172.17.0.2",
                    "IPPrefixLen": 16,
                    "IPv6Gateway": "",
                    "GlobalIPv6Address": "",
                    "GlobalIPv6PrefixLen": 0,
                    "MacAddress": "02:42:ac:11:00:02",
                    "DriverOpts": null
                }
            }
        }
```

Check for **"IPAddress": "172.17.0.2"**. And this is what you will refer to in another containers (e.g APIM) to connect to MySQL.
