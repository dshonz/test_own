# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	config.vm.define "web" do |web|
		config.vm.box = "peru/ubuntu-18.04-server-amd64"
                config.vm.network "forwarded_port", guest: 80, host: 8085
		web.vm.hostname = "test-ownCloud"
                web.vm.network "private_network", ip: "192.168.10.244"
#		config.ssh.port = 5643

                config.vm.provider "virtualbox" do |web|
#                       web.name = "test-ownCloud"
                        web.cpus = 2
                        web.memory = "1024"
                end
	
	end

	config.vm.provision "ansible" do |ansible|
		ansible.verbose = "v"
		ansible.playbook = "ansible/testbox_ownCloud.yml"
		ansible.sudo = true
	end
#	config.vbguest.auto_update = false

end
