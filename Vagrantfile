$samplescript = <<SCRIPT
yum install -y httpd
systemctl enable httpd
systemctl start httpd
SCRIPT

Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.hostname = "myhost"
  config.vm.network "private_network", ip: "192.168.50.10"
#  config.vbguest.installer_arguments = ['--nox11', '-- --do']
#  config.vm.synced_folder "src/", "/var/www/html"


  config.vm.provision "shell", inline: $samplescript

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = "2"
  end

  if Vagrant.has_plugin?("vagrant-vbguest")
      config.vbguest.auto_update = false
  end

end
