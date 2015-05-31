# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/vivid64"
  config.vm.network "private_network", ip: "192.168.34.10"

    config.vm.provider "virtualbox" do |v|
      v.memory = 2048
      v.cpus = 2
    end

    config.vm.define :docker do |docker|
    end

    # Ansible provisioner.
    config.vm.provision "ansible" do |ansible|
      ansible.groups = {
        "docker" => ["vagrant-docker-1"],
      }

      ansible.playbook = "provisioning/playbook.yml"
      ansible.sudo = true
    end
end
