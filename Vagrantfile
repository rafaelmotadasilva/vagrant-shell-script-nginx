# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.network "public_network"
  config.vm.provision "shell", path: "install_nginx.sh"
  config.vm.synced_folder "website/", "/var/www/html"
end
