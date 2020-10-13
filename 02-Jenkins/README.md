# Jenkins Demo

## Download Jenkins & Install Java JDK
```
  mkdir 02-Jenkins
  apt-get install default-jdk -y
  java -version
  wget https://get.jenkins.io/war-stable/2.249.2/jenkins.war
  mv jenkins.war /root/

```

## Setup Jenkins to run on custom port : 9090

```
  java -jar jenkins.war --httpPort=9090 & 
```

## Get the initial Credentials
```
 cat .jenkins/secrets/initialAdminPassword

```

## Open the Jenkins in Browser for further Setup.

### http://MasterNodeIP:9090
### Supply the initialadminPassword 
### Install Suggested Plugins


## Maven Package Build Manually 

```
apt-get install maven -y 
mvn --version 
git pull 
cd 02-Jenkins/petclinic-code
mvn clean 
mvn compile 
mvn test
mvn package
```
