# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "catatsuy/wheezy"

  config.vm.network :forwarded_port, guest: 3000, host: 3000

  # config.vm.network :private_network, ip: "192.168.33.10"

  config.vm.synced_folder ".", "/vagrant", type: "rsync", rsync__exclude: [".git/", "vendor/", ".bundle", "Gemfile.lock"]

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision "shell", path: "https://raw.github.com/catatsuy/dotfiles/master/debian.sh"

end
