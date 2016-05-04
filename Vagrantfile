Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/trusty64'
  config.ssh.insert_key = false

  config.vm.provision "ansible" do |ansible|
    ansible.sudo = true
    ansible.playbook = '/Users/nirajkhanal/Desktop/Vagrant/vagrant_getting_started/VagrantFiles/Ansible/Provisioning/playbook.yml'
  end
end

