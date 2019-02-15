# Docker Container H2

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
