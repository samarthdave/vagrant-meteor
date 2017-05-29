Vagrant.configure("2") do |config|

  # my computer doesn't seem to like the 64 bit version
  config.vm.box = "ubuntu/trusty32"

  # sync folders so that you can edit with sublime or a text editor of your choice
  # and have those changes reflected on the vm
  config.vm.synced_folder './workspace', '/home/vagrant/workspace'

  # forward the port so you can access on any device in the network
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.provider "virtualbox" do |vb|
    vb.customize ["modifyvm", :id, "--memory", "1024"]
    # the next line is for the network setup
    # wifi on the vm doesn't work w/o this
    vb.customize ["modifyvm", :id, "--nictype1", "Am79C973"]
  end

  config.vm.provision "shell", path: "bootstrap.sh"

end