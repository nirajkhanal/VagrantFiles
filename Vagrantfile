$install_ansible = <<SCRIPT
apt-get -y install software-properties-common
apt-add-repository ppa:ansible/ansible
apt-get -y update
apt-get -y install ansible

SCRIPT

Vagrant.configure(2) do |config|
  config.vm.box = 'ubuntu/trusty64'
  config.vm.provision 'shell', inline: $install_ansible
  # Patch for https://github.com/mitchellh/vagrant/issues/6793
  config.vm.provision "shell" do |s|
    s.inline = '[[ ! -f $1 ]] || grep -F -q "$2" $1 || sed -i "/__main__/a \\    $2" $1'
    s.args = ['/usr/bin/ansible-galaxy', "if sys.argv == ['/usr/bin/ansible-galaxy', '--help']: sys.argv.insert(1, 'info')"]
  end
  config.vm.provision :ansible_local do |ansible|
    ansible.sudo = true
    ansible.playbook = '../Ansible/Provisioning/playbook.yml'
  end
end

