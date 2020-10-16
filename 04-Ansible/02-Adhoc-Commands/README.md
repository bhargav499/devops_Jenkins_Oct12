## Ansible Module Documentations
```
ansible-doc -l
ansible-doc command
```



## Ansible AdHoc Command with modules

```
ansible web -i 02-Adhoc-Commands/inventory -m command -a 'df -h'
ansible web -i 02-Adhoc-Commands/inventory -m command -a 'uname -a'
cat /etc/*-release
ansible web -i 02-Adhoc-Commands/inventory -m command -a 'cat /etc/*-release'
ansible web -i 02-Adhoc-Commands/inventory -m command -a 'cat /etc/os-release'
ansible web -i 02-Adhoc-Commands/inventory -m command -a 'cat /etc/*-release'
ansible web -i 02-Adhoc-Commands/inventory -m shell -a 'cat /etc/*-release'
```
