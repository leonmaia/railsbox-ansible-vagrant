# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.require_version ">= 1.5.0"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.hostname = "railsbox"

  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
  config.vm.box = "ubuntu/trusty64"


  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "3600"]
  end

  config.vm.network :private_network, ip: "192.168.50.4"
  config.vm.network :forwarded_port, guest: 4200, host: 4200
  config.vm.network :forwarded_port, guest: 3000, host: 3000

  ENV['VAGRANT_SYNCED_FOLDER'] ||= "~/Projects"
  config.vm.synced_folder ENV['VAGRANT_SYNCED_FOLDER'], "/vagrant", type: 'nfs'

  config.vm.provision :ansible do |ansible|
   ansible.playbook = "playbook.yml"
 end
end
