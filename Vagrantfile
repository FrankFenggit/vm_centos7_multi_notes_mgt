# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "centos7"

  config.hostmanager.enable = true
  config.hostmanager.manage_guest = true
  config.hostmanager.manage_host = true
  
  #config.winnfsd.logging = "on"
  #config.winnfsd.uid = 1
  #config.winnfsd.gid = 1

  config.vm.define "node1" do |node1|
    node1.vm.network "private_network", ip: "192.168.4.100"
    node1.vm.hostname = "node1.frank.com"
    node1.vm.synced_folder "./node1", "/vagrant",create: "true",type: "nfs"
    node1.bindfs.bind_folder "/vagrant","/vagrant", 
      force_user: 'vagrant', force_group: 'vagrant', o: "nonempty",perms:"a+rwx"
  end
  
  config.vm.define "node2" do |node2|
    node2.vm.network "private_network", ip: "192.168.4.101"
    node2.vm.hostname = "node2.frank.com"
    node2.vm.synced_folder "./node2", "/vagrant",create: "true",type: "nfs"
    node2.bindfs.bind_folder "/vagrant","/vagrant", 
      force_user: 'vagrant', force_group: 'vagrant', o: "nonempty",perms:"a+rwx"
  end
  
  config.vm.define "node3" do |node3|
    node3.vm.network "private_network", ip: "192.168.4.102"
    node3.vm.hostname = "node3.frank.com"
    node3.vm.synced_folder "./node3", "/vagrant",create: "true",type: "nfs"
    node3.bindfs.bind_folder "/vagrant","/vagrant", 
      force_user: 'vagrant', force_group: 'vagrant', o: "nonempty",perms:"a+rwx"
  end

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
  # config.vm.network "private_network", ip: "192.168.33.10"

  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
  # config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  # end
  #
  # View the documentation for the provider you are using for more
  # information on available options.

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. Please see the
  # documentation for more information about their specific syntax and use.
  # config.vm.provision "shell", inline: <<-SHELL
  #   apt-get update
  #   apt-get install -y apache2
  # SHELL
end
