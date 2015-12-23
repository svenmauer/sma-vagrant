# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.synced_folder "C://Users//SvenMeikel//vagrant-share", "/home/vagrant/smaprojects"
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.provision "shell", inline: <<-SHELL
  sudo apt-key adv --y --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
    echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list    
    apt-get update
    apt-get install -y g++
    curl -sL https://deb.nodesource.com/setup_4.x | bash -
    sudo apt-get install -y nodejs
    sudo apt-get install -y build-essential
    sudo apt-get install -y mongodb-org
    sudo apt-get install -y git
    rm -rf /home/vagrant/.vim
    git clone https://github.com/svenmauer/dotvim.git /home/vagrant/.vim
    git clone https://github.com/gmarik/vundle.git /home/vagrant/.vim/bundle/vundle
    rm -rf /home/vagrant/.vimrc
    cp /home/vagrant/.vim/.vimrc /home/vagrant/
  SHELL
end
