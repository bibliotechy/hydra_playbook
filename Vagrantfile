# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
    config.vm.box = "geerlingguy/centos7" 
    config.vm.network "forwarded_port", guest: 8996, host: 8996
    config.vm.network "forwarded_port", guest: 80, host: 8180

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "playbook.yml"
	    ansible.host_key_checking = false 
	    ansible.inventory_path = "inventory/vagrant/"
	    ansible.limit = "all"
      ansible.verbose = "vv"
      ansible.raw_arguments = ["--vault-password-file=~/.vault"]
    end
  end
