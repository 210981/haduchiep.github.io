# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "geerlingguy/centos7"
  
  config.vm.hostname = "gitlab.local"

  if Vagrant.has_plugin?("vagrant-vbguest")
    config.vbguest.auto_update= false
  end
  
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  config.vm.network "private_network", ip: "10.0.0.10"
  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync_exclude: [".git/"]
  
  config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  vb.name ="gitlab.local"
  #   # Customize the amount of memory on the VM:
  vb.memory = "4096"
  end
end
