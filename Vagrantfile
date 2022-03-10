# -*- mode: ruby -*-
# vi: set ft=ruby :
RAM = 10024
CPU = 1
IP = "10.0.0.10"

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/xenial64"
  config.vm.provider "virtualbox" do |v|
    v.memory = RAM
    v.cpus = CPU
  end
  config.vm.hostname = "webserver"
  config.vm.network "private_network", ip: IP
  config.vm.provision "ansible_local" do |ansible|
    ansible.install = true
    ansible.install_mode = "pip"
    ansible.pip_install_cmd = "curl https://bootstrap.pypa.io/pip/3.5/get-pip.py | sudo python"
    ansible.playbook = "nginx.yml"
  end
end
