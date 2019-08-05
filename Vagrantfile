# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure(2) do |config|
        config.vm.box = "centos/7"
        config.vm.box_check_update = false
        config.vm.hostname = "centos"

        config.vm.network :private_network, ip: "192.168.100.101"
        config.vm.provision :shell, :inline => "sudo sed -i 's/PasswordAuthentication no/PasswordAuthentication yes/g' /etc/ssh/sshd_config; sudo systemctl restart sshd;", run: "always"
        config.vm.provision "file", source: "~/.ssh/localvagrant_rsa.pub", destination: "/home/vagrant/.ssh/authorized_keys"

end