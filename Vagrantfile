# -*- mode: ruby -*-
# vi: set ft=ruby :

# LOG

Vagrant.configure("2") do |config|

  config.vm.box = 'almalinux/8'
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "ELK_NGINX.yml"
  end

config.vm.define "LOG" do |log|
  log.vm.network "private_network", ip: "192.168.56.24"


  log.vm.provider "virtualbox" do |vb|
    vb.memory = "4096"
  end
  log.vm.host_name = 'LOG'
  
  (0..3).each do |i|
   log.vm.disk :disk, size: "10GB", name: "disk-#{i}"
  end
 end


# WEB

  config.vm.define "WEB" do |web|
    web.vm.network "private_network", ip: "192.168.56.25"
    web.vm.host_name = 'WEB'
    web.vm.provider :virtualbox do |vb|
      vb.memory = "4096"
    end
    
  end

end
