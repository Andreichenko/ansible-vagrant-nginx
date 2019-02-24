Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname ="ansible.test.instance"
  config.vm.network :private_network, ip: "192.168.30.10"

  config.ssh.insert_key=false

  config.vm.provider "virtualbox" do |vb|
    # Virtual instance
    vb.name = "ansible-machine-1"
    vb.gui = false
    vb.memory = "512"
  end
  config.vm.provision "shell", inline: <<-SHELL
  yum install -y epel-release
  yum install - y python-pip
  pip install -U pip
  pip install -U ansible
  SHELL
end