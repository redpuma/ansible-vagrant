# Ansible demonstration

This repo contains an example of how to use Vagrant to test Ansible roles and playbooks in this instance using Ubuntu.

## Requirements

The role can be included for use against an Ubuntu host with [Ansible](http://docs.ansible.com/ansible/intro_installation.html) version 2.0.
Or using the Vagrantfile then [Vagrant 1.8.1+](https://www.vagrantup.com/downloads.html) and [VirtualBox 5.0x](https://www.virtualbox.org/wiki/Downloads) are required.

## Instructions

Assuming Vagrant is ready clone this repo locally

  vagrant up

This will create two [Ubuntu Trusty64](https://atlas.hashicorp.com/ubuntu/boxes/trusty64) hosts using Ansible to prepare the hosts for management by Ansible.
- ansible management host
- ansible managed host
See the 'provisioning' directory for detail.

Once the two hosts have been provisioned the roles in the 'ansible/roles' directory can be run using the playbooks in the root of that directory.

```
# login to ansible controller host
vagrant ssh ans02.dev

# change to ansible user
sudo su - ansible

# change directory to ansible code directory
cd /usr/local/ansible

# run ping test
ansible -i inventories/vagrant/localdev all -m ping

# run a test playbook to view vars
ansible-playbook -i inventories/vagrant/localdev test.yml

# run playbook for the UFW install task
ansible-playbook -i inventories/vagrant/localdev install-ufw.yml

```




