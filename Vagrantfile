# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Change host name and allocated memory
  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--name", "openmrs-dev", "--memory", "1024"]
  end

  config.vm.box = "precise64"

  # The url from where the 'config.vm.box' box will be fetched if it
  # doesn't already exist on the user's system.
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # config.vm.boot_mode = :gui

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.synced_folder "code", "/vagrant/code"

  # Set Vagrant to use Puppet for provisioning and where to find the manifests/modules
  config.vm.provision :puppet do |puppet|
    puppet.module_path = "modules"
     puppet.manifests_path = "manifests"
     puppet.manifest_file  = "base.pp"
   end
end
