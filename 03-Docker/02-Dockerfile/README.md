# To Build a Docker Image from Dockerfile


## Create a Build WorkSpace 

## Crate your custom Dockerfile into WorkSpace.

## Excute the below Build Commands
```
docker build -t my-apache-ubuntu:v1 -f Dockerfile . 

docker run -d --name test-web-app-01 my-apache-ubuntu:v1

docker inspect test-web-app-01 | grep -i "ContainerIP"

curl <containerIP>
```
