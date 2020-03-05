# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "renkeju/ubuntu-desktop-bionic"
  config.vm.box_version = "0.0.1"

  config.vm.provider "virtualbox" do |vb|
    vb.customize [
      "modifyvm", :id,
      "--nictype1", "virtio",
      "--cpus", "2",
      "--memory", "4096",
      "--description", "ubuntu desktop ansible playbook",
      "--name", "ubuntu-desktop-ansible-playbook",
      "--graphicscontroller", "vmsvga"
	]
  end
end
