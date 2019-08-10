# centos_vm

Creates minimal Centos7 vm from Vagrantfile.
Provison playbook gets/installs Kamailio and associated dependencies on the vm.

requirements:
-vagrant
-ansible
-virtualbox

clone this repo
vagrant up

To configure as SIP Proxy server:
-vagrant ssh into vm
-sudo -i
-vi /etc/kamailio/kamailio.cfg
--dG at top of file to clear
--
