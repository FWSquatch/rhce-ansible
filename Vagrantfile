# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "geerlingguy/centos8"
  config.ssh.insert_key = false
  config.vm.provider "virtualbox"

  config.vm.provider :virtualbox do |v|
    v.memory = 1536
    v.cpus = 1
    v.linked_clone = true
  end

  # Define three VMs with static private IP addresses.
  boxes = [
    { :name => "control", :ip => "192.168.88.2" },
    { :name => "node1", :ip => "192.168.88.101" },
    { :name => "node2", :ip => "192.168.88.102" },
    { :name => "node3", :ip => "192.168.88.103" },
  ]

  # Provision each of the VMs.
  boxes.each do |opts|
    config.vm.define opts[:name] do |config|
      config.vm.hostname = opts[:name] + ".centos8.test"
      config.vm.network :private_network, ip: opts[:ip]
    end
  end
end
