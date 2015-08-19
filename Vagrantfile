# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  config.vm.box = "leopard/rwtrusty64"

   config.vm.network "forwarded_port", guest: 3000, host: 3000

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
   config.vm.synced_folder "./", "/home/vagrant/apps"

   config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
   end

   config.vm.provision "shell", inline: <<-SHELL
     sudo apt-get update
     gem install rails
   SHELL
end
