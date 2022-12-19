# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "debian/bullseye64"
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.ssh.insert_key = false

  config.vm.provider "virtualbox" do |vb|
    vb.name = "polemarch"
    vb.memory = "512"
    vb.cpus = 1
  end
  
  config.vm.hostname = "polemarch"
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbooks/vagrant.yaml"
    ansible.become = true
  end

end
