# DevOps Demo Repo.

## Topic 1 - Git Version Cantrol

## Git Version Cantrol

### Register yourself to github.com & done the verfication. 

### Create a new repo with the name : DevOps-Accenture-2020Oct12. 

### Go to the Lab Environment & Clone the with following command
```
vagrant.exe up 
vagrant.exe ssh master
sudo su - 
```

### Let clone the newly created repo. 

```
apt-get update; apt-get install git -y
git clone https://github.com/amitvashisttech/devops-accenture-2020Oct12.git   -- Replace with your Repo URL.  
```


### Go inside the Repo & Create your first commit 
```
cd devops-accenture-2020Oct12/
echo "Hello World" > Hello.txt
git status
git add Hello.txt
git status
git commit -m "New file - Hello.txt"
git log
git push
```
