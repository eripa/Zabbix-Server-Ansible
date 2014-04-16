# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.

 config.vm.define :zabbix do |zabbix|
    zabbix.vm.box = "chef/centos-6.5"
    zabbix.vm.hostname = "zabbix"
    zabbix.vm.network "private_network", ip: "192.168.50.4"
    #zabbix.vm.network "public_network"

    zabbix.vm.provision "ansible" do |ansible|
        ansible.playbook = "zabbix-server.yml"
        ansible.sudo = true
        #ansible.verbose = "vvvv"
        #ansible.inventory_path = "hosts"
        ansible.extra_vars = {
          "virtualbox_client" => true
        }
    end

  end
end