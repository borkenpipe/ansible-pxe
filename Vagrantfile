# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "fedora/25-bloud-base"
  config.vm.hostname = "erpxe"
  config.nfs.functional = false
  config.vm.define :erpxe do |erpxe|
  end

  # Ansible provisioner.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.sudo = true
  end
end
