# -*- mode: ruby -*-
# vi: set ft=ruby :
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty32"
  config.vm.box_check_update = false
  config.vm.hostname = "ansible"
  config.ssh.forward_agent = true
  config.vm.network "private_network", ip: "192.168.33.10"
#  config.vm.synced_folder "./app", "/opt/software/app"

  config.vm.provision "ansible" do |ansible|
        ansible.playbook = "tacos.yml"
        ansible.inventory_path = "inventory/dev"
        ansible.limit = 'all'
        ansible.raw_arguments  = [
          "--private-key=.vagrant/machines/default/virtualbox/private_key"
        ]
  end

end
