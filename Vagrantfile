# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = true
    ansible.groups = {
      "nomad" => ["nomad01"]
    }
  end

  config.vm.provider "libvirt" do |vm|
    vm.memory = "4096"
    vm.qemu_use_session = false
  end
end
