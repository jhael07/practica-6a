# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANT_API_VERSION = "2"

Vagrant.configure(VAGRANT_API_VERSION) do |config|
  
  # Definir VM1
  config.vm.define "web1" do |web1|
    web1.vm.box = "ubuntu/bionic64"
    web1.vm.network "private_network", ip: "192.168.33.10"
    web1.vm.synced_folder "./html", "/var/www/html", owner: "www-data", group: "www-data"
    web1.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      systemctl enable apache2
      systemctl start apache2
    SHELL
  end

  # Definir VM2
  config.vm.define "web2" do |web2|
    web2.vm.box = "ubuntu/bionic64"
    web2.vm.network "private_network", ip: "192.168.33.11"
    web2.vm.synced_folder "./html", "/var/www/html", owner: "www-data", group: "www-data"
    web2.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install -y apache2
      systemctl enable apache2
      systemctl start apache2
    SHELL
  end
end
