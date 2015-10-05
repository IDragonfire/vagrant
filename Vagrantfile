# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

box = 'trusty64'
box_url = 'https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'
hostname = 'develop'

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = box
  config.vm.box_url = box_url

  config.vm.provider "virtualbox" do |v|
    v.memory = 512
  end

  config.vm.synced_folder ".", "/vagrant"

  # -- Networking ------------------------------------------
  config.vm.hostname = hostname
 
  # API
  config.vm.network :forwarded_port, guest: 80, host: 8080
  # My Sql DB
  config.vm.network :forwarded_port, guest: 3306, host: 3306

  # Services
  config.vm.network :forwarded_port, guest: 2000, host: 2000
  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 4000, host: 4000
  config.vm.network :forwarded_port, guest: 5000, host: 5000
  config.vm.network :forwarded_port, guest: 6000, host: 6000
  config.vm.network :forwarded_port, guest: 7000, host: 7000

  # -- Provisioning ----------------------------------------
  provision_dir = "vagrant/provision"

  vm = config.vm

  vm.provision :docker do |docker|
    # Start here docker container
  end

    vm.provision :shell, path: "#{provision_dir}/vagrant_provision"
  vm.provision :shell, path: "#{provision_dir}/python_provision"
end
