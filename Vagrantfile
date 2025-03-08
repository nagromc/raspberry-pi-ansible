Vagrant.configure("2") do |config|
  config.vm.box = "debian/bookworm64"
  config.vm.hostname = "raspi-vbox.local"
  config.vm.provider :virtualbox do |vb|
    vb.name = "raspberrypi-dev"
  end

  config.vm.network "private_network", type: "dhcp"
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook-debian-to-raspios.yaml"
  end
end
