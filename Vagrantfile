# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Use ~/vagrant.d/insecure_private_key for all systems
  config.ssh.insert_key = false
  # Disable default /vagrant share
  config.vm.synced_folder ".", "/vagrant", disabled: true
  config.vm.provider :virtualbox do |v|
    v.memory = 512
    v.cpus = 1
  end

  config.vm.define "debian11" do |debian11|
    debian11.vm.box = "debian/bullseye64"
    debian11.vm.hostname = "debian11"
    debian11.vm.network "private_network", ip: "10.0.0.64"
  end

end
