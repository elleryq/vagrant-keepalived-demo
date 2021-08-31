# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  config.vm.define "master" do |u1|
    u1.vm.box = "generic/centos8"
    u1.vm.hostname = "master"
    u1.vm.network :private_network, ip: "192.168.60.11"
    u1.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
    end
    u1.vm.provision "ansible" do |ansible|
      ansible.playbook = "install-master.yml"
    end
  end

  config.vm.define "slave" do |u2|
    u2.vm.box = "generic/centos8"
    u2.vm.hostname = "slave"
    u2.vm.network :private_network, ip: "192.168.60.12"
    u2.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
    end
    u2.vm.provision "ansible" do |ansible|
      ansible.playbook = "install-slave.yml"
    end
  end

  config.vm.define "u3" do |u3|
    u3.vm.box = "generic/centos8"
    u3.vm.hostname = "backend"
    u3.vm.network :private_network, ip: "192.168.60.13"
    u3.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
    end
    u3.vm.provision "ansible" do |ansible|
      ansible.playbook = "install-httpd.yml"
    end
  end

  config.vm.define "u4" do |u4|
    u4.vm.box = "generic/centos8"
    u4.vm.hostname = "backend"
    u4.vm.network :private_network, ip: "192.168.60.20"
    u4.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--memory", 512]
    end
  end
end
