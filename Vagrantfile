# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"



Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

#Misma clave para todas las máquinas
config.ssh.insert_key = false

 config.vm.define "load-balancer" do |host|
  host.vm.hostname = "load-balancer"
  host.vm.box = "ubuntu/trusty64"
  host.ssh.username = "vagrant"
  host.vm.network "forwarded_port", guest: 80, host: 8000 
  host.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--nic2", "intnet"]
  end
 
 end

 
 config.vm.define "webserver1" do |host|
  host.vm.hostname = "webserver1"
  host.vm.box = "ubuntu/trusty64"
  host.ssh.username = "vagrant"

  host.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--nic2", "intnet"] 
  end
 end

 config.vm.define "webserver2" do |host|
  host.vm.hostname = "webserver2"
  host.vm.box = "ubuntu/trusty64"
  host.ssh.username = "vagrant"

  host.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--nic2", "intnet"] 
  end
 
 end

end
