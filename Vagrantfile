# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # Every Vagrant virtual environment requires a box to build off of.

 config.vm.define :zabbix do |zabbix|
    zabbix.vm.box = "chef/centos-6.5"
    zabbix.vm.hostname = "zabbix"
    #zabbix.vm.provider :virtualbox do |vb|
    #  vb.gui = true
    #end

    zabbix.vm.provision "ansible" do |ansible|
        ansible.playbook = "zabbix-server.yml"
        ansible.sudo = true
        #ansible.verbose = "vvvv"
        ansible.extra_vars = {
          "virtualbox_client" => true
        }
    end

  end
end