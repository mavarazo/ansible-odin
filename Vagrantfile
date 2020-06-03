Vagrant.configure("2") do |config|
  config.vm.box = "hashicorp/bionic64"
  config.vm.network "private_network", ip: "192.0.2.10"

  config.vm.network "forwarded_port", guest: 80, host: 8080, id: "traefik_web"
  config.vm.network "forwarded_port", guest: 443, host: 8443, id: "traefik_websecure"
  config.vm.network "forwarded_port", guest: 8080, host: 8088, id: "traefik_dashboard"

  #
  # Run Ansible from the Vagrant Host
  #
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
  end

end