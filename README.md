
## Vagrant+Ansible+Nginx+MySQL 

- Requires Ansible 1.2 or newer
- Using Ubuntu 12.04 or higher
- Virtualbox 
- Vagrant

This setup requires Virtualbox and Vagrant and Ansible. 
The Vagrantfile included here define two VMs: a web using nginx and db using mysql. 


### Installing Ansible is documented at http://docs.ansible.com/intro_installation.html#installation
  
  Simple installation using Ubuntu PPA on Ubuntu 12.04: 

    $ sudo add-apt-repository ppa:rquillo/ansible
    $ sudo apt-get update
    $ sudo apt-get install ansible     


### Running Vagrant, docs are at http://docs.vagrantup.com/v2/:

    $ mkdir vagrant-test
    $ cd vagrant-test
    $ vagrant box add precise64 http://files.vagrantup.com/precise64.box


### Running db and web VM's: 

    $ git clone https://github.com/cocoy/vagrant_ansible.git
    $ cd vagrant_ansible 
    $ vagrant up web 
    $ vagrant up db 

### Provisioning after more changes with Ansible Playbooks:

    $ vagrant provision web 
    $ vagrant provision db 

### Notes:

   * Adding jenkins roles from: https://github.com/ICTO/ansible-jenkins
   * Adding apache2/php5 roles from: https://github.com/laggyluke/ansible-role-apache2

### Using Ansible Galaxy Added
   * How to Setup is here http://bit.ly/1gRToit 

