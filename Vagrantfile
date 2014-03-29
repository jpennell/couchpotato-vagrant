Vagrant.require_plugin "vagrant-berkshelf"
Vagrant.require_plugin "vagrant-omnibus"

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "precise64"
  config.omnibus.chef_version = :latest
  config.berkshelf.enabled = true

  config.vm.network "forwarded_port", guest: 5050, host: 5002

  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "couchpotato"
  end

end
