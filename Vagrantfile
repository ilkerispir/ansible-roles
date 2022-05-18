# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ilker/ubuntu20.04"
  config.vm.box_version = "1.0"
  config.vm.box_check_update = true
  config.vm.network :private_network, ip: "192.168.2.10"
  config.vm.provider "virtualbox"

  config.vm.provider "virtualbox" do |vb|
    vb.cpus = 2
    vb.memory = "4096"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end
