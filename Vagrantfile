# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
	
	config.vm.provision "shell", path: "configuration/config.sh"

	config.vm.define "host01" do |host01|
		host01.vm.box = "ubuntu/xenial64"
		host01.vm.network "private_network", ip: "192.168.33.10"
		host01.vm.hostname = "host01"
		host01.vm.provider "virtualbox" do |vb|
			vb.name = "host01"
		    vb.customize ["modifyvm", :id, "--audio", "none"]
		end
		host01.vm.provision "shell", inline: <<-SHELL
		SHELL
		host01.vm.provision "shell", path: "hosts/host01.sh"
		host01.vm.provision "shell", path: "control-plane/control-plane.sh"
	end

	config.vm.define "host02" do |host02|
		host02.vm.box = "ubuntu/xenial64"
		host02.vm.network "private_network", ip: "192.168.33.11"
		host02.vm.hostname = "host02"

		host02.vm.provider "virtualbox" do |vb|
			vb.name = "host02"
			vb.customize ["modifyvm", :id, "--audio", "none"]
		end
		host02.vm.provision "shell", inline: <<-SHELL
		SHELL
		host02.vm.provision "shell", path: "hosts/host02.sh"
	end
	
	config.vm.define "host03" do |host03|
		host03.vm.box = "ubuntu/xenial64"
		host03.vm.network "private_network", ip: "192.168.33.12"
		host03.vm.hostname = "host03"

		host03.vm.provider "virtualbox" do |vb|
			vb.name = "host03"
		    vb.customize ["modifyvm", :id, "--audio", "none"]
		end
		host03.vm.provision "shell", inline: <<-SHELL
		SHELL
		host03.vm.provision "shell", path: "hosts/host03.sh"
	end

end
