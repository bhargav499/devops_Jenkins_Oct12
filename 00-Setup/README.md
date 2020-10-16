# Lab Setup 

##Please find the lab Requirement. 
``` 
	1. One Physical Machine per participant ( 16GB RAM, Core i5 CPU & 500GB Hard Disk ).
	2. Virtualization should be enabled on all the physical machines. 
	3. BaseOS Windows 10 or higher x64 Bit Operating System.
	4. Install 7 Zip. https://www.7-zip.org/a/7z1801-x64.exe
	5. Install Virtual Box. https://download.virtualbox.org/virtualbox/5.1.28/VirtualBox-5.1.28-117968-Win.exe
	6. Install Vagrant.  https://releases.hashicorp.com/vagrant/2.0.4/vagrant_2.0.4_x86_64.msi
	7. Install Cmder.   https://github.com/cmderdev/cmder/releases/download/v1.3.5/cmder.zip
	8. Install Notepad++ https://notepad-plus-plus.org/repository/7.x/7.5.6/npp.7.5.6.Installer.x64.exe
	9. Open Internet Connectivity. ( No Proxy ) 

 ```

## Vagrant Setup 
1. Open the cmder /git client / Shell / cmd & Create Vagrant DevOps folder Structure. 
```
mkdir -p vagrant-setup/devops
cd vagrant-setup/devops

```

2. Copy Past the below content, in order 3 VM Setup. 
```
vim Vagrantfile

# -*- mode: ruby -*-
# vi: set ft=ruby :

ENV['VAGRANT_NO_PARALLEL'] = 'yes'

Vagrant.configure(2) do |config|


  # Master Server
  config.vm.define "master" do |master|
    master.vm.box = "ubuntu/xenial64"
    master.vm.hostname = "master.example.com"
    master.vm.network "private_network", ip: "172.31.0.100"
    master.vm.provider "virtualbox" do |v|
      v.name = "master"
      v.memory = 4048
      v.cpus = 2
      # Prevent VirtualBox from interfering with host audio stack
      v.customize ["modifyvm", :id, "--audio", "none"]
    end
  end

  NodeCount = 2

  # Worker Nodes
  (1..NodeCount).each do |i|
    config.vm.define "worker#{i}" do |workernode|
      workernode.vm.box = "ubuntu/xenial64"
      workernode.vm.hostname = "worker#{i}.example.com"
      workernode.vm.network "private_network", ip: "172.31.0.10#{i}"
      workernode.vm.provider "virtualbox" do |v|
        v.name = "worker#{i}"
        v.memory = 1024
        v.cpus = 1
        # Prevent VirtualBox from interfering with host audio stack
        v.customize ["modifyvm", :id, "--audio", "none"]
      end
    end
  end

end

```


3. Run Vagrant Up to provision the VM
```
vagrant up 
vagrant status
master                    running (virtualbox)
worker1                   running (virtualbox)
worker2                   running (virtualbox)
```


4. Shutdown & Destroy
```
vagrant halt 
vagrant destroy 
```
