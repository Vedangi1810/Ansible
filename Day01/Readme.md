Ansible:

Configuration management tool
Perform task on multiple system 
=======================================================================================================
Ansible primarily based on : Python
Purpose of ansible.cfg file : To set ansbile options and default 
ansible-playbook command: executes an ansible playbook that describes set of task, configurations and policies 
                          to group of target machines
ansible module used to copy file from control machine to host in ansible : copy
ansible module used to install packages on remote host : package [search on google: ansible modules package]
how to specify multiple jhost in an ansible inventory file : define host groups using square brackets []
Ansible Fact:
    Information about a managed node, discovered by Ansible
How can you run ansible playbook against a specific set of hosts:
    use ansible-playbook cpmmand with --limit option
ansible module to manage aws resources: ec2
=========================================================================================================


Terraform: Build/Provision the infrastructure (to build vm on cloud)
Ansible: Manage/Configure/Update the infrastructure (to patch/update os)


chef and ansible both are configuration management tool
mostly used ansible
chef : Pull based mechanism
ansible : Push based mechanism
============================================================================================

Installation:

==========================================
Configuration:
sudo vim /etc/ansible/hosts

[servers]
server_1 ansible_host=public_ip/host_name
server_2 ansible_host=public_ip

[prd]
server_3 ansible_host=public_ip
==========================================

mkdir keys
cd keys (add ansible-master-key.pem)
pwd
/home/ubuntu/keys
==========================================

use scp command to copy .pem from  download from local to ansible-master
sudo vim /etc/ansible/hosts

[all:vars]
ansible_python_interpreter=/usr/bin/python3
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/keys/ansible-master-key.pem
==========================================

Ansible modules are units of code that can control system resources or execute system commands  [-m]
ansible servers -m ping
ansible servers -a "free -h" [-a adhoc command]
ansible servers -a "sudo apt update"

ansble prd -m ping

ansible-inventory --list
==========================================

Playbook:

mkdir playbooks

ansible-playbook date_play.yml
ansible-playbook -v date_play.yml

