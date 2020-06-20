# -*- mode: ruby -*-
# vi: set ft=ruby :

ubuntus = {
  "host0" => "192.168.33.10",
  "host1" => "192.168.33.11",
  "host2" => "192.168.33.12"
}

centosis = {
  "host3" => "192.168.33.20",
  "host4" => "192.168.33.21",
  "host5" => "192.168.33.22"
}

ubuntu-c = {
  "host6" => "192.168.33.30"
}

Vagrant.configure("2") do |config|
  ubhosts.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/bionic64"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256]
      end
    end
  end
end

Vagrant.configure("2") do |config|
  centosis.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "centos/7"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256]
      end
    end
  end
end


Vagrant.configure("2") do |config|
  ubuntu-c.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/bionic64"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256]
      end
    end
  end
end
