## Create EI Image

```
docker build -t anupamgogoi/wso2ei-630 .
```

## Run EI
```
docker run -d -t --name wso2ei-630 -p 9443:9443 -p 8243:8243 -p 8280:8280 anupamgogoi/wso2ei-630

```
