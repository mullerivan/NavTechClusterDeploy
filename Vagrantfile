# vim: ft=ruby:expandtab:tabstop=2:softtabstop=2:shiftwidth=2

Vagrant.configure("2") do |config|
  config.vm.box = "ARTACK/debian-jessie"
#################Servidor de mails
    config.vm.define vm_name = "in_server" do |in_server|
      in_server.vm.network "forwarded_port", guest: 25, host: 9025      
      in_server.vm.network :private_network, ip: "10.22.22.20"
      in_server.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbooks/in_server.yml"
        ansible.host_key_checking = false
      end
      in_server.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "512"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
      end
    end
################Servidor web
    config.vm.define vm_name = "web" do |web|
      web.vm.network "forwarded_port", guest: 80, host: 9080      
      web.vm.network :private_network, ip: "10.22.22.30"
      web.vm.provision "ansible" do |ansible|
        ansible.playbook = "playbooks/web.yml"
        ansible.host_key_checking = false
      end
      web.vm.provider :virtualbox do |vb|
        vb.customize ["modifyvm", :id, "--memory", "512"]
        vb.customize ["modifyvm", :id, "--cpus", "1"]
      end
    end
end
