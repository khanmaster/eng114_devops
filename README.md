# What is DevOps
## Why DevOps - Benefits
### Role of DevOps

- Most used commands
- update & upgrade ubuntu `sudo apt-get update -y`
- upgrade `sudo apt-get upgrade -y`
- install nginx `sudo apt-get install nginx -y`
- check nginx status `systemctl status nginx` or `stop` or `start` or `restart`
- who am I `uname` or `uname -a`
- where am I `pwd`
- how to create a folder in linux `mkdir dir-name`
- how to check folder/file `ls` or `ls -a`
- change dir `cd name-dir`
- come out/back of/from the current location `cd ..`
- how to create a file `touch filename` or `nano file-name`
- move test.txt from current location to devops folder
- cut paste `mv test.txt devops` copy  `cp path_of_data path_of_destination`
  

#### File permissions
- READ `r` WRITE `w` `x` 
- how to check file permission `ll`
- change permissions`chmod permission file-name`
![]()

### Bash Scripting
- create a file called provision.sh
- change permission of this file `chmod +x provision.sh`
- first line `MUST BE` starting with `#!/bin/bash`
- update & upgrade
- installed nginx
- start nginx
- `enable nginx` 
  
- stoped then started 
- To run our Script `sudo ./provsion.sh` 

```
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"
  config.vm.network "private_network", ip: "192.168.10.100"
  config.hostsupdater.aliases = ["development.local"]

  # Synced app folder
  config.vm.synced_folder ".", "/home/vagrant/app"

  # Provisioning
  config.vm.provision "shell", path: "environment/provision.sh"

end
```






```
sudo apt-get install nodejs -y
sudo apt-get install python-software-properties
curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
sudo apt-get install nodejs -y
sudo npm install pm2 -g
```
### Creating Variables in Linux




### Reverse Proxy with Nginx
- edit the defult file and insert the code to redirect the traffic
- delete the file and replace with pre-configured file
- ` sudo rm -rf default
- cp or ln default from localhost to default location of reverse proxy file
- test it `sudo nginx -t`
- `restart` and `enable`
-  
- 
![](images/Screenshot%20(280).png)
#####
- How to check process running in linux
- `top` or `ps aux`
- How to kill a process `sudo kill process-id`
- How to use piping | to sort out or short list process
- how to use `head` and `tail`
- 
  
### setting up mongodb
```
sudo apt-get update -y

sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv D68FA50FEA312927

echo "deb https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list

sudo apt-get update -y
sudo apt-get upgrade -y

# sudo apt-get install mongodb-org=3.2.20 -y

sudo apt-get install -y mongodb-org=3.2.20 mongodb-org-server=3.2.20 mongodb-org-shell=3.2.20 mongodb-org-mongos=3.2.20 mongodb-org-tools=3.2.20

# if mongo is is set up correctly these will be successful
sudo systemctl restart mongod
sudo systemctl enable mongod
```
