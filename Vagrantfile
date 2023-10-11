# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  config.vm.network "private_network", ip: "192.168.56.40"

  # Disable synced folder (enabled by default, but we don't need it)
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.hostname = "doy-ckan"

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
  
    vb.memory = "4096"
    vb.cpus = "4"
    
    vb.name = "doy-ckan"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/main.yml"
  end
end
