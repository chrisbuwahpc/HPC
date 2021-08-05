# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
  Vagrant.configure("2") do |config|
   config.vm.box = "UWAHPC/cits5507.box"
   config.vm.box_version = "2021.1.0"
  end
  

  # argument is a set of non-required options.
  #config.vm.synced_folder "images", "/home/vagrant/images"
  config.vm.synced_folder "data", "/home/vagrant/data"
  config.vm.synced_folder "scripts", "/home/vagrant/scripts"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
   config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
     vb.cpus = "4"
  #   # Customize the amount of memory on the VM:
     vb.memory = "4096"
   end

   config.vm.host_name = "uwahpc"

   
end
