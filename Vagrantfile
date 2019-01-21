# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/xenial64"

  config.vm.network "forwarded_port", guest: 80, host: 80
  config.vm.network "private_network", ip: "192.168.56.101"
  
  config.vm.provision "ansible_local" do |ansible|
    ansible.verbose = true
    ansible.limit = "all"
    ansible.install = true
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "hosts"
    ansible.become = true
  end

end
