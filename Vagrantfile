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

  # Enterprise Linux boxes
  config.vm.define "centos7" do |centos7|
    centos7.vm.box = "generic/centos7"
    centos7.vm.hostname = "centos7"
    centos7.vm.network "private_network", ip: "10.0.0.10"
  end
  config.vm.define "rocky8" do |rocky8|
    rocky8.vm.box = "generic/rocky8"
    rocky8.vm.hostname = "rocky8"
    rocky8.vm.network "private_network", ip: "10.0.0.11"
  end
  config.vm.define "rocky9" do |rocky9|
    rocky9.vm.box = "generic/rocky9"
    rocky9.vm.hostname = "rocky9"
    rocky9.vm.network "private_network", ip: "10.0.0.12"
  end
  
  # SUSE boxes
  config.vm.define "opensuse15_5" do |opensuse15_5|
    opensuse15_5.vm.box = "opensuse/Leap-15.5.x86_64"
    opensuse15_5.vm.hostname = "opensuse15.5"
    opensuse15_5.vm.network "private_network", ip: "10.0.0.21"
  end

  # Debian boxes
  config.vm.define "debian11" do |debian11|
    debian11.vm.box = "debian/bullseye64"
    debian11.vm.hostname = "debian11"
    debian11.vm.network "private_network", ip: "10.0.0.30"
  end
  config.vm.define "debian12" do |debian12|
    debian12.vm.box = "debian/bookworm64"
    debian12.vm.hostname = "debian12"
    debian12.vm.network "private_network", ip: "10.0.0.31"
  end

  # Ubuntu boxes
  config.vm.define "ubuntu2004" do |ubuntu2004|
    ubuntu2004.vm.box = "ubuntu/focal64"
    ubuntu2004.vm.hostname = "ubuntu2004"
    ubuntu2004.vm.network "private_network", ip: "10.0.0.40"
  end
  config.vm.define "ubuntu2204" do |ubuntu2204|
    ubuntu2204.vm.box = "ubuntu/jammy64"
    ubuntu2204.vm.hostname = "ubuntu2204"
    ubuntu2204.vm.network "private_network", ip: "10.0.0.41"
  end
end
