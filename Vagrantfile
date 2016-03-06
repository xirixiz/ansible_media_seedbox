# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "vivid"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/vivid/current/vivid-server-cloudimg-amd64-vagrant-disk1.box"
  #config.vm.box = "willy"
  #config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/wily/current/wily-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "main.yml"
    ansible.ask_vault_pass = false
  end

  config.vm.network :forwarded_port, host: 8080, guest: 443
  config.vm.network :forwarded_port, host: 8000, guest: 8000
  config.vm.network :forwarded_port, host: 8010, guest: 8010
  config.vm.network :forwarded_port, host: 8020, guest: 8020
  config.vm.network :forwarded_port, host: 8030, guest: 8030
  config.vm.network :forwarded_port, host: 8040, guest: 32400
  config.vm.network :forwarded_port, host: 32400, guest: 32400
end
