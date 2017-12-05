Vagrant.configure("2") do |config|
  config.vm.define "master" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vm.hostname = "master.ansible.com"
    subconfig.vm.network :private_network, ip: "10.0.0.10"
  end

  config.vm.define "node1" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vm.hostname = "node1.ansible.com"
    subconfig.vm.network :private_network, ip: "10.0.0.20"
  end

  config.vm.define "node2" do |subconfig|
    subconfig.vm.box = "ubuntu/xenial64"
    subconfig.vm.hostname = "node2.ansible.com"
    subconfig.vm.network :private_network, ip: "10.0.0.30"
  end
  # Install avahi on all machines
  config.vm.provision "shell", inline: <<-SHELL
  apt-get install -y avahi-daemon libnss-mdns
  SHELL
end
