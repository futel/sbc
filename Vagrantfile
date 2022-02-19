VAGRANTFILE_API_VERSION = "2"

# $samplescript = <<SCRIPT
# yum install -y httpd
# systemctl enable httpd
# systemctl start httpd
# SCRIPT

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.define "default"  
  config.vm.box = "generic/rocky8"
  config.vm.synced_folder ".", "/vagrant",
    :mount_options => ["dmode=777,fmode=777"]

  #config.vbguest.installer_arguments = ['--nox11', '-- --do']
  #config.vm.provision "shell", inline: $samplescript

  config.vm.provision "baseinstall", type: "ansible" do |ansible|  
    ansible.playbook = "deploy/baseinstall_playbook.yml"
  end

  config.vm.provider :virtualbox do |vb|
    vb.memory = 1024 # current prod is 512mb, this is for convenience
    # this creates vboxnet0 and vboxnet1, with pingable eth1 on vboxnet1
    config.vm.network "private_network", type: "dhcp", :adapter => 2    
    # uncomment to disable headless mode
    # vb.gui = true
    # vb.cpus = "2"               # XXX    
  end

end

