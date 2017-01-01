# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.synced_folder ".", "/project"

  config.vm.provision "shell", inline: <<-SHELL

    echo "Update package lists..."
    apt-get update

    echo "Install python"
    sudo apt-get -y install python-pip

    echo "Set the vagrant user as the owner of files in /project"
    sudo chown -R vagrant /project

  SHELL

end
