# -*- mode: ruby -*-
# vi: set ft=ruby :

ubuntus = {
  "ubuntu1" => "192.168.33.10",
  "ubuntu2" => "192.168.33.11",
  "ubuntu3" => "192.168.33.12"
}

centosis = {
  "centos1" => "192.168.33.20",
  "centos2" => "192.168.33.21",
  "centos3" => "192.168.33.22"
}

ubuntuc = {
  "ubuntu-c" => "192.168.33.30"
}

Vagrant.configure("2") do |config|
  ubuntus.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/bionic64"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256, "--cpus", 1, "--cpuexecutioncap", "10"]
      config.vm.synced_folder "data/", "/vagrant"
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
          v.customize ["modifyvm", :id, "--memory", 256, "--cpus", 1, "--cpuexecutioncap", "30"]
      config.vm.synced_folder "data/", "/vagrant"
      end
    end
  end
end

Vagrant.configure("2") do |config|
  ubuntuc.each do |name, ip|
    config.vm.define name do |machine|
      machine.vm.box = "ubuntu/bionic64"
      machine.vm.hostname = "%s" % name
      machine.vm.network :private_network, ip: ip
      machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.customize ["modifyvm", :id, "--memory", 256, "--cpus", 1, "--cpuexecutioncap", "50"]
      config.vm.synced_folder "data/", "/vagrant"
      config.vm.provision "shell", inline: "apt update && apt install sshpass -y"
      end
    end
  end
end
