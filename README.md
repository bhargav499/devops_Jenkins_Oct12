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
### Git Diff. 
```
   59  git diff 51e2a1b..10a7e2d
   60  ls
   61  mkdir  Hello_World
   62  echo "Hello World" > Hello_World/helloworld.txt
   63  git status
   64  git add .
   65  git status
   66  git commit -m "New Dir Hello_World"
   67  git log
   68  git diff 6a47bd..51e2a1b
   69  git diff HEAD~1
   70  git diff HEAD~2
   71  git diff HEAD~3
   72  git diff HEAD~4
   73  git diff HEAD~5
   74  ls
   75  git diff HEAD~2..HEAD~3
   76  git show HEAD
   77  git log
```


### Git CheckOut, Rests & Clean 

```
 83  mv Hello_World HelloWorld
   84  ls
   85  rm -rf Hello.txt
   86  git status
   87  git add .
   88  git status
   89  git commit -m "Hello File has been removed & Dir has been Renamed"
   90  ls
   91  vim README.md
   92  ls
   93  cat README.md
   94  vim README.md
   95  git status
   96  git checkout README.md
   97  git status
   98  vim README.md
   99  ls
  100  git checkout
  101  rm -rf HelloWorld
  102  git status
  103  git checkout
  104  git status
  105  git checkout
  106  git checkout main
  107  git log
  108  ls
  109  git log
  110  git checkout
  111  ls
  112  git reset
  113  ls
  114  git reset --soft HEAD
  115  ls
  116  git reset --soft HEAD~1
  117  ls
  118  git status
  119  git commit -m "Redo"
  120  ls
  121  git commit -m "Redo"
  122  git status
  123  ls
  124  git reset --hard HEAD~1
  125  ls
  126  git status
  127  ls
  128  mv Hello_World HelloWorld
  129  git status
  130  git add . ; git commit -m "Undo with Hard Rest"
  131  git log
  132  ls
  133  mkdir temp
  134  for i in "01..10"; do echo "Hello Temp $i" > temp/temp-file_$i.txt; done
  135  ls
  136  apt-get install tree -y
  137  tree .
  138  for i in {01..10}; do echo "Hello Temp $i" > temp/temp-file_$i.txt; done
  139  tree .
  140  cat temp/temp-file_01.txt
  141  cat temp/temp-file_02.txt
  142  ls
  143  git add . ; git commit -m "Added Couple of Temp files"
  144  git log
  145  git diff HEAD~1
  146  ls
  147  git clean -f temp/*
  148  tree temp/
  149  git status
  150  git add .
  151  git status
  152  git clean -f temp/temp-file_01.txt
  153  ls -ltr temp/
  154  git clean --help
  155  s
  156  ls
  157  mkdir temp2
  158  ls
  159  for i in {01..10}; do echo "Hello Temp $i" > temp2/temp-file_$i.txt; done
  160  tree temp2/
  161  ls
  162  git clean temp2/temp-file_01.txt
  163  git clean -f temp2/temp-file_01.txt
  164  git clean
  165  git clean -f
  166  ls
  167  cd temp
  168  cd ..
  169  ls
  170  cd temp2/
  171  ls
  172  cd ..
  173  ls
  174  git clean -n
  175  git clean -n --help
  176  git clean -f temp2/*

```



### Git Credential Helper
```
 209  git config credential.helper store
  210  git push https://github.com/amitvashisttech/devops-accenture-2020Oct12.git

```

### Git Logging

```
233  git clone https://github.com/jquery/jquery.git
  234  ls
  235  cd jquery/
  236  ls
  237  git log
  238  git log --oneline
  239  git log --oneline | wc -l
  240  git log --oneline --graph
  241  git log --shortlog
  242  git shortlog
  243  git shortlog -sne


```
