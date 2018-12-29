Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
 
  config.vm.define "ansible" do |ansible|
    ansible.vm.box = "ubuntu/xenial64"
    ansible.vm.hostname = "ansible-server"
    ansible.vm.network "private_network", ip: "192.168.100.9"
 
    config.vm.provider "virtualbox" do |ansible|
      ansible.name = "ansible-server"
      ansible.cpus = 1
      ansible.memory = "1024"
    end
 
    ansible.vm.provision "shell", path: "ansible.sh"
  end
 
  config.vm.define "web" do |web|
    web.vm.box = "ubuntu/xenial64"
    web.vm.hostname = "web-server"
    #web.vm.network "private_network", type: "dhcp"
    web.vm.network "private_network", ip: "192.168.100.10"
 
    config.vm.provider "virtualbox" do |web|
      web.name = "web-server"
      web.cpus = 1
      web.memory = "1024"
    end
 
    web.vm.provision "shell", path: "web.sh"
  end
 
  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/xenial64"
    db.vm.hostname = "db"
    #db.vm.network "private_network", type: "dhcp"
    db.vm.network "private_network", ip: "192.168.100.11"
 
    config.vm.provider "virtualbox" do |db|
      db.name = "db"
      db.cpus = 1
      db.memory = "1024"
    end
 
    db.vm.provision "shell", path: "db.sh"
  end
 
end