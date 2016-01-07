# ansible
fih ansible test

# need a headless account on all servers and with ssh public key
/etc/sudoers
fih_ci    ALL=(ALL)       NOPASSWD:ALL

# Ansible installation
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible

# Ansible usage
- Cmd
$ ssh-agent bash
$ ssh-add ~/.ssh/id_rsa

ansible test -m ping (test is group name in /etc/ansible/hosts)
ansible test -a "/bin/hostname"
ansible test -a "/usr/bin/whoami" -u fih --sudo --ask-sudo-pass

ansible test -m yum -a "name=mysql state=present" 	(Ensure a package is installed, but don’t update it)
ansible test -m yum -a "name=nc state=absent"		(Ensure a package is not installed)

ansible test -m service -a "name=sshd state=started"	(Ensure a service is started)

ansible -m setup test

# Ansible Doc
http://docs.ansible.com/ansible-tower/?utm_campaign=Tower+Trial+Download&utm_source=hs_automation&utm_medium=email&utm_content=11745256&_hsenc=p2ANqtz--op-YCeoQB1e2HuuzKxy1_-ZqebfuJXOk5BhblmWuI2mXtR-w1OS5EHtzFvxv_azPKmGiFTk0bdkt6OC86QB0gT61N4Q&_hsmi=11745256

# Ansible Tower
sudo apt-key adv --keyserver-options http-proxy="http://10.57.35.31:8080" --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
