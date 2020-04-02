# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get dist-upgrade
    apt-get install -y make python3 python3-pip sdcc wget
    pip3 install -r /vagrant/requirements.txt
    rm -rf /tmp/msx
    git clone https://gist.github.com/35e406ed26cea6bae20c.git /tmp/msx
    cd /vagrant
    mkdir /vagrant/msx
    bash /tmp/msx/sdcc_configure_msx_support ./msx
    make superclean && make   
    exit 0
  SHELL
end
