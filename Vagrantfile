# -*- mode: ruby -*-
# vi: set ft=ruby :
VM_BOX  = 'ubuntu/focal64'
NETWORK = 'forwarded_port'
GUEST_PORT = 80
HOST_PORT = 9000
Vagrant.configure(2) do |config|
  config.vm.box = VM_BOX
  config.vm.provision "shell", path: "scripts/install.sh"
  config.vm.network NETWORK, guest: GUEST_PORT, host: HOST_PORT
#  config.vm.synced_folder '/host/path', '/guest/path', SharedFoldersEnableSymlinksCreate: false
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
  end
  config.vm.provision 'shell', inline: <<-SHELL
    echo 'ubuntu:ubuntu' | sudo chpasswd
  SHELL
end
