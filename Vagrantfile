# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |cluster|
  # All Vagrant configuration is done here. The most common configuration
  # options are documented and commented below. For a complete reference,
  # please see the online documentation at vagrantup.com.

  # Every Vagrant virtual environment requires a box to build off of.

#cluster.vm.define "ldapvm" do |config|
#  config.vm.box = "centos/7"
#  config.ssh.insert_key = false
#  config.vm.provider :virtualbox do |vb, override|
#    vb.customize ["modifyvm", :id, "--memory", "512"]
#    vb.customize ["modifyvm", :id, "--cpus", "1"]
#  end
#  config.vm.hostname = "ldapvm"
#  config.vm.network :private_network, ip: "172.16.2.9"
#  config.vm.provision "ansible" do |ansible|
#    ansible.playbook = "site.yml"
#    ansible.groups = {
#      "tag_Vagrant_True" => ["ldapvm"],
#      "tag_Vagrant_local" => ["ldapvm"],
#      "tag_Name_ldapvm" => ["ldapvm"],
#    }
#  end
#end

cluster.vm.define "tower" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "4096"]
    vb.customize ["modifyvm", :id, "--cpus", "2"]
  end
  config.vm.hostname = "tower"
  config.vm.network :private_network, ip: "172.16.2.42"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "tag_Vagrant_True" => ["tower"],
      "tag_Vagrant_local" => ["tower"],
      "tag_Name_Tower" => ["tower"],
    }
  end
end

cluster.vm.define "demovm1" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "demovm1"
  config.vm.network :private_network, ip: "172.16.2.5"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "tag_Vagrant_True" => ["demovm1"],
      "tag_Vagrant_local" => ["demovm1"],
      "tag_Name_demovm" => ["demovm1"],
    }
  end
end

cluster.vm.define "demovm2" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "demovm2"
  config.vm.network :private_network, ip: "172.16.2.6"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "tag_Vagrant_True" => ["demovm2"],
      "tag_Vagrant_local" => ["demovm2"],
      "tag_Name_demovm" => ["demovm2"],
    }
  end
end

cluster.vm.define "demovm3" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "demovm3"
  config.vm.network :private_network, ip: "172.16.2.7"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "tag_Vagrant_True" => ["demovm3"],
      "tag_Vagrant_local" => ["demovm3"],
      "tag_Name_demovm" => ["demovm3"],
    }
  end
end

cluster.vm.define "demovm4" do |config|
  config.vm.box = "centos/7"
  config.ssh.insert_key = false
  config.vm.provider :virtualbox do |vb, override|
    vb.customize ["modifyvm", :id, "--memory", "512"]
    vb.customize ["modifyvm", :id, "--cpus", "1"]
  end
  config.vm.hostname = "demovm4"
  config.vm.network :private_network, ip: "172.16.2.8"
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "site.yml"
    ansible.groups = {
      "tag_Vagrant_True" => ["demovm4"],
      "tag_Vagrant_local" => ["demovm4"],
      "tag_Name_demovm" => ["demovm4"],
    }
  end
end

end
