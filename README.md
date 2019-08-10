# centos_vm

Creates centos7 vm from Vagrantfile.
Provison playbook gets/installs kamailio and associated dependencies on the centos7 vm.

requirements:
-vagrant
-ansible
-virtualbox

git clone this repo
vagrant up

To configure as SIP Proxy server to pass through to a futel asteriskserver vm:
-vagrant ssh into centos7 vm
-sudo -i
-vi /etc/kamailio/kamailio.cfg
--dG at top of kamailio.cfg to clear the file
--[COPY PASTE from here https://blog.voipxswitch.com/2015/03/27/kamailio-basic-sip-proxy-all-requests-setup/]
--edit kamailio.cfg to define 
    (1) IP address -- use IP of this centos7 vm
    (2) switch IP address -- use IP of asterisk vm 
    (3) destination -- use IP of asterisk vm 
--save changes and exit vi
-systemctl daemon-reload
-systemctl enable kamailio
-exit vagrant ssh
-vagrant reload
