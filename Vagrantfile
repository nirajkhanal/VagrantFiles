Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false

  config.vm.provision "ansible_local" do |ansible|
    ansible.provisioning_path = "../vagrant_getting_started/VagrantFiles"
    ansible.playbook = "provisioning/playbook.yml"
  end
end


