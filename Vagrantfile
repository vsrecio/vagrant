# -*- mode: ruby -*-
# vi: set ft=ruby :
 
Vagrant.configure("2") do |config|
    # Type of the box
    config.vm.box = "centos/7"
 
    # Configs for web server 1
    config.vm.define "ops-manager" do |ops|
        # Configs for virtual machine entry in Oracle VM VirtualBox
        ops.vm.provider :virtualbox do |vb_config|
            vb_config.name = "Ops Manager for MongoDB"
            vb_config.memory = 8192
        end
        # Terminal name
        ops.vm.hostname = "ops-manager"
        # IP address to access from host machine
        ops.vm.network "private_network", ip: "192.168.50.10"
        ops.vm.network "forwarded_port", guest: 8080, host: 8080
    end
 
    # Configs for web server 2
    config.vm.define "mongo" do |db|
        # Configs for virtual machine entry in Oracle VM VirtualBox
        db.vm.provider :virtualbox do |vb_config|
            vb_config.name = "MongoDB Server"
        end
        # Terminal name
        db.vm.hostname = "db"
        # IP address to access from host machine
        db.vm.network "private_network", ip: "192.168.50.20"
        db.vm.network "forwarded_port", guest: 27017, host: 27017

        #Data Share
        #db.vm.synced_folder "./data", "/vagrant_data"
    end
end