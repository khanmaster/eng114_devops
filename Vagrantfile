# Vagrant.configure("2") do |config|

#   config.vm.box = "ubuntu/xenial64"
  
#   # add a private network between localhost & VM using ip
#   config.vm.network "private_network", ip: "192.168.10.100"

#   # Synced app folder
#                  # cp everything from current location create a folder called app - copy everything from localhost
#   config.vm.synced_folder ".", "/home/vagrant/app"

#   #v mac users ip 192.168.10.10

#   # Provisioning
#   config.vm.provision "shell", path: "app/environment/provision.sh"
# end


# multi-machine code block

Vagrant.configure("2") do |config|
  config.vm.define "app" do |app|
    app.vm.box = "ubuntu/xenial64"
    app.vm.network "private_network", ip: "192.168.10.100"
    app.vm.synced_folder ".", "/home/vagrant/app"
    
    app.vm.provision "shell", path: "app/environment/provision.sh", privileged: false
    
  end

  # Let's create our db machine
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/xenial64"
    db.vm.network "private_network", ip: "192.168.10.150"
    
  end
end




