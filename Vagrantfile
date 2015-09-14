# -*- mode: ruby -*-
# vi: set ft=ruby :

# Virtual machine used to build the debian package.

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.synced_folder "debian", "/home/vagrant/debian"

  config.vm.provision "shell", inline: <<-EOF
apt-get update
apt-get install -y build-essential devscripts debhelper scons
  EOF
end
