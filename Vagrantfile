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

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.become = true
    ansible.verbose = false
    ansible.compatibility_mode = "2.0"
    ansible.vault_password_file = "~/.vault_pass"
    ansible.extra_vars = { 
      ansible_python_interpreter: "/usr/bin/python3" 
    }
  end

end
