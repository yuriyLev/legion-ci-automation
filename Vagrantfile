Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/xenial64"
  config.ssh.insert_key = false
  config.vm.hostname = "jenkins"

  config.vm.network "forwarded_port", guest: 443, host: 443
  config.vm.network "forwarded_port", guest: 9091, host: 9091

  config.vm.provider "virtualbox" do |vb|
    vb.gui = false
    vb.memory = "3072"
  end

  config.vm.provision "ansible_local" do |ansible|
#    ansible.verbose = "v"
    ansible.playbook = "jenkins.yaml"
  end
end
