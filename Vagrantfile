# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |cluster|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.

cluster.vm.define "tower" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "4096"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
  end
  config.vm.hostname = "tower"
  config.vm.network :private_network, ip: "10.42.0.42"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

cluster.vm.define "host1" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "host1"
  config.vm.network :private_network, ip: "10.42.0.6"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

cluster.vm.define "host2" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "host2"
  config.vm.network :private_network, ip: "10.42.0.7"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

cluster.vm.define "host3" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "host3"
  config.vm.network :private_network, ip: "10.42.0.8"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

cluster.vm.define "host4" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "host4"
  config.vm.network :private_network, ip: "10.42.0.9"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

cluster.vm.define "host5" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "host5"
  config.vm.network :private_network, ip: "10.42.0.10"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "demo.yml"
  end
end

end