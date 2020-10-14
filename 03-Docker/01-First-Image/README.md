# Creating First Container Image. 

## Let's start a CentOS Container & Make it WebServer

```
docker run -it --name webserver01 centos:7 /bin/bash
XXXXXXXXXXY1# yum install httpd -y 
XXXXXXXXXXY1# httpd -k start 
XXXXXXXXXXY1# curl localhost
XXXXXXXXXXY1# echo "Welcome to Webserver Powered by Docker" > /var/www/html/info.html
XXXXXXXXXXY1# curl localhost/info.html
XXXXXXXXXXY1# echo "/usr/sbin/httpd -k start" >> /root/.bashrc
XXXXXXXXXXY1# ctl p q 
```

## Make a Image from existing Container
```
docker commit -p -m "My Httpd WebServer" webserver01 centos-test-httpd:v1
```  


## Lets spin up couple of containers with newly built webserver image 

```
docker run -itd --name webserver-test-01 centos-test-httpd:v1 /bin/bash
docker run -itd --name webserver-test-02 centos-test-httpd:v1 /bin/bash
```

## Verfiy the web service status 
```
docker exec webserver-test-01 ps aux 
docker inspect webserver-test-01
curl <IPAddress of webserver-test-01>/info.html 

```
