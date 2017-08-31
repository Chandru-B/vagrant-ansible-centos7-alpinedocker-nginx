VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "centos/7"
  config.vm.network :private_network, ip: "192.168.55.55"
  config.vm.network "forwarded_port", guest: 8080, host: 80  
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.name = "dockertest.text"
    v.memory = 1024
    v.cpus = 2
    v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    v.customize ["modifyvm", :id, "--ioapic", "on"]
  end

  # Enable provisioning with Ansible.
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provision/centos7.yml"
  end

end
