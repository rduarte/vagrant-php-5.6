# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
    config.vm.box = "ubuntu/trusty32"

    config.vm.network :private_network, ip: "192.168.10.56"
    config.vm.network :forwarded_port, guest: 80, host: 80
    config.vm.network :forwarded_port, guest: 3306, host: 3306
    config.vm.network :forwarded_port, guest: 10081, host: 10081

    config.vm.provision :shell, :path => "install.sh"

    config.vm.synced_folder ".", "/vagrant", :mount_options => ["dmode=777", "fmode=666"]

    # If true, then any SSH connections made will enable agent forwarding.
    # Default value: false
    # config.ssh.forward_agent = true

    # Share an additional folder to the guest VM. The first argument is
    # the path on the host to the actual folder. The second argument is
    # the path on the guest to mount the folder. And the optional third
    # argument is a set of non-required options.
    config.vm.synced_folder "/Users/ricardo/git/", "/var/www/php"
end
