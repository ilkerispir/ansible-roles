# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # Box
  config.vm.box = "ubuntu/focal64"
  config.vm.box_version = "20211026.0.0"

  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", type: "virtualbox"

  # Provider & Specs
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 1
  end

  config.vm.define "ilker-vm" do |machine|
    machine.vm.hostname = "ilker-vm"
    machine.vm.network :private_network, ip: "192.168.56.11"
    config.vm.network "forwarded_port", guest: 80, host: 8080
  end

  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "auto"
    ansible.playbook = "playbook.yml"
    ansible.inventory_path = "hosts"
    ansible.limit = "all"
    ansible.become = true
    ansible.verbose = false
    #ansible.config+file = 'ansible.cfg'
  end
end
