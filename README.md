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

### Git Global Config 
```
git config --global user.name "Amit Vashist"
git config --global user.email "amitvashist7@outlook.com"
git config --list 
```


### Git Object Storage
```
echo "Apple Pie" | git hash-object --sidin
echo "Apple Pie" | git hash-object --stdin
echo "Apple Pie" | git hash-object --stdin -w
ls -ltr .git/objects/
ls -ltr .git/objects/23/
git cat-file 23991897e13e47ed0adb91a0082c31c82fe0cbe5 -t
git cat-file 23991897e13e47ed0adb91a0082c31c82fe0cbe5 -p
echo "Bannana Shake" | git hash-object --stdin -w
git cat-file f10d03c5ab66794c28c07e582527bebee8ed2d7f -p
```

