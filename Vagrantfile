# -*- mode: ruby -*-
# vi: set ft=ruby :

#  useradd -m chris --groups sudo
#  su -c "printf 'cd /home/chris\nsudo su chris' >> .bash_profile" -s /bin/sh vagrant
#SCRIPT

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
   Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-18.04"

  # argument is a set of non-required options.
  config.vm.synced_folder "images", "/home/vagrant/images"
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

   config.vm.host_name = "kaya2"

   config.vm.provision "shell", inline: <<-SHELL
     apt-get update
#
     apt-get install -y tcl8.6 zip
     ln -s /usr/bin/tclsh8.6 /usr/bin/tclsh
     apt-get install -y environment-modules

     git clone  https://github.com/chrisbpawsey/maali-1.5.git
#
     chown -R vagrant:vagrant maali-1.5
     cd maali-1.5

     sudo -H -u vagrant bash -c './install_scripts/Install_icrar_vagrant.sh'
     echo "module path variable is $MODULEPATH"
     sudo -H -u vagrant bash -c './maali -t maali -v 1.5h -c vagrant -d'
     sudo -H -u vagrant bash -c 'source ~/.bashrc'
     sudo -H -u vagrant bash -c 'cp ~/maali-1.5/install_scripts/Install_HPC_ubuntu_18.sh ~/setup.sh'
     cd 
     cd scripts
     git clone https://github.com/chrisbpawsey/HDF5_examples.git
     
  SHELL

end
