# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure('2') do |config|

  # Ensure we use our vagrant private key
  #config.ssh.insert_key = false
  #config.ssh.private_key_path = '~/.vagrant.d/insecure_private_key'

  config.vm.define 'cpan' do |machine|
    machine.vm.box = "bento/centos-7.1"
    #machine.vm.box = "ubuntu/trusty64"
    #machine.vm.box = "ubuntu/precise64"
    #machine.vm.box = "debian/jessie64"
    #machine.vm.box = "debian/wheezy64"
    #machine.vm.box = "chef/centos-7.1"
    #machine.vm.box = "chef/centos-6.6"

    machine.vm.network :private_network, ip: '192.168.33.10'
    machine.vm.hostname = 'cpan.local'
    machine.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'tests/test.yml'
      ansible.sudo = true
      #ansible.inventory_path = 'vagrant-inventory'
      #ansible.host_key_checking = false
    end

  end

end
