# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  
  config.vm.define "web01" do |web01|
    web01.vm.box = "ubuntu/trusty64"
    web01.vm.hostname = "web01"
    #web01.vm.network "private_network", type: "dhcp"
    web01.vm.network :private_network, ip:"172.28.128.11", netmask:"24"
    web01.vm.network :forwarded_port, guest: 22, host: 2222, host_ip: "0.0.0.0", id: "ssh", auto_correct: true
  end

  config.vm.define "db01" do |db01|
    db01.vm.box = "ubuntu/trusty64"
    db01.vm.hostname = "db01"
    db01.vm.network :private_network, ip:"172.28.128.21", netmask:"24"
    # Enable ssh forward agent
    db01.vm.network :forwarded_port, guest: 22, host: 2222, host_ip: "0.0.0.0", id: "ssh", auto_correct: true
  end

end

