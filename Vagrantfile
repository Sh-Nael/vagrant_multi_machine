# -*- mode: ruby -*-
# vi: set ft=ruby :
#Vagrant development environment requires a box. You can search for
# boxes at https://atlas.hashicorp.com/search.
Vagrant.configure("2") do |config|
  config.vm.define "web01", primary: true do |web01|
    web01.vm.box = "ubuntu/trusty64"
    web01.vm.hostname = 'web01'
    web01.vm.box_url = "ubuntu/trusty64"

    web01.vm.network :private_network, ip: "172.16.0.101"
    web01.vm.network :forwarded_port, guest: 22, host: 10122, id: "ssh"


    web01.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "web01"]
    end
  end

  config.vm.define "web02" do |web02|
    web02.vm.box = "ubuntu/trusty64"
    web02.vm.hostname = 'web02'
    web02.vm.box_url = "ubuntu/trusty64"

    web02.vm.network :private_network, ip: "172.16.0.102"
    web02.vm.network :forwarded_port, guest: 22, host: 10123, id: "ssh"


    web02.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "web02"]
    end
  end

  config.vm.define "db" do |db|
    db.vm.box = "ubuntu/trusty64"
    db.vm.hostname = 'db'
    db.vm.box_url = "ubuntu/trusty64"

    db.vm.network :private_network, ip: "172.16.0.103"
    db.vm.network :forwarded_port, guest: 22, host: 10224, id: "ssh"

    db.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
      v.customize ["modifyvm", :id, "--memory", 512]
      v.customize ["modifyvm", :id, "--name", "db"]
    end
  end

end
