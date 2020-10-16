						
[Prod] 
172.31.0.[100:180]
172.31.0.[201:240]

[UAT]
172.31.0.[186:200]
172.31.0.[246:250]


[Staging] 
172.31.0.[181:185]
172.31.0.[241:245]


[WebServer]
172.31.0.[100:200]

[DBServer]
172.31.0.[201:250]


[Ansible]
172.31.0.101

						
						
						
# All Prod 						
ansible Prod -i inventory -u vagrant -m ping -k 	

# All UAT 						
ansible UAT -i inventory -u vagrant -m ping -k 

# All Prod & UAT Both Groups 						
ansible Prod:UAT -i inventory -u vagrant -m ping -k 

# Prod WebServers
ansible 'WebServers:&Prod' -i inventory -u vagrant -m ping -k 


# UAT DBServers
ansible 'DBServers:&UAT' -i inventory -u vagrant -m ping -k 


# Prod WebServers except Ansible Server
ansible 'WebServers:&Prod:!ansible' -i inventory -u vagrant -m ping -k 
					
