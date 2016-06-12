V_NAME="rublog"

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.ssh.forward_agent = true

  config.vm.hostname = V_NAME

  config.vm.provision "shell", inline: V_PROVISION

  config.vm.provider "virtualbox" do |v|
    v.name   = V_NAME
    v.memory = 2048
  end
end

V_PROVISION = <<SCRIPT
apt-get update
apt-get upgrade -y
apt-get install -y ruby-dev
gem install redcarpet
SCRIPT