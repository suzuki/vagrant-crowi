Vagrant.configure(2) do |config|
  config.ssh.forward_agent = true

  config.vm.box = "ubuntu/trusty64"
  config.vm.network 'forwarded_port', guest: 3000, host: 8080
  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "playbook.yml"
    ansible.verbose = "vv"
    ansible.raw_ssh_args = ['-o ForwardAgent=yes -o ControlMaster=auto -o ControlPersist=1800s']
  end
end
