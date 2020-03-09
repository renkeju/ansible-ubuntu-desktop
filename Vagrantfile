# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "renkeju/ubuntu-desktop-bionic"
  config.vm.box_version = "0.0.2"

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

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.install_mode = "pip"
    ansible.become = true
    ansible.compatibility_mode = "2.0"
    ansible.extra_vars = { 
      ansible_python_interpreter: "/usr/bin/python3" 
    }
  end

end
