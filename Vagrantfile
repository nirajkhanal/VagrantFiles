Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/trusty64'
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = '../Ansible/Provisioning/playbook.yml'
  end
end

