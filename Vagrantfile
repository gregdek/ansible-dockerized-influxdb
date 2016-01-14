# -*- mode: ruby -*-
# vi: set ft=ruby :

#Vagrant file for libvirt/kvm and virtualbox provider

# check if plugin is installed on system
unless Vagrant.has_plugin?("vagrant-adbinfo")
  raise "vagrant-adbinfo plugin is not installed, run `vagrant plugin install vagrant-adbinfo` to install the plugin."
end

Vagrant.configure(2) do |config|
  config.vm.box = "projectatomic/adb"

  # Setup a DHCP based private network
  config.vm.network "private_network", type: "dhcp"

  # Forward ports, which are the same ports specified
  # in the role
  config.vm.network "forwarded_port", guest: 8083, host: 8083
  config.vm.network "forwarded_port", guest: 8084, host: 8084
  config.vm.network "forwarded_port", guest: 8086, host: 8086
  config.vm.network "forwarded_port", guest: 8090, host: 8099

  config.vm.provider "libvirt" do |libvirt, override|
    libvirt.driver = "kvm"
    libvirt.memory = 1024
    libvirt.cpus = 2
  end

  config.vm.provider "virtualbox" do |vbox, override|
    vbox.memory = 1024
    vbox.cpus = 2

    # Enable use of more than one virtual CPU in a virtual machine.
    vbox.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
