# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
 
  config.vm.box = "UWAHPC/cits5507.box"
  config.vm.box_version = "2021.1.0"
  
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
