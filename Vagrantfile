# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "web" do |web|
      web.vm.box = "precise64"
      web.vm.network :private_network, ip: "192.168.33.10"
      web.ssh.forward_agent = true
      #web.vm.synced_folder ".", "/vagrant", :nfs => true
      web.vm.network :forwarded_port, host: 8080, guest: 8080

      web.vm.provision "ansible" do |ansible| 
        ansible.sudo = true
        ansible.playbook = "playbooks/web.yml"
        #ansible.verbose = "vvv"
        #ansible.inventory_path= "vagrant_hosts"
        ansible.host_key_checking = false
      end 
  end
  config.vm.define "db" do |db|
      db.vm.box = "precise64"
      db.vm.network :private_network, ip: "192.168.33.20"
      db.ssh.forward_agent = true
      #db.vm.synced_folder ".", "/vagrant", :nfs => true
      db.vm.network :forwarded_port, host: 3366, guest: 3306 

      db.vm.provision "ansible" do |ansible| 
        ansible.sudo = true
        ansible.playbook = "playbooks/db.yml"
        #ansible.verbose = "vvv"
        #ansible.inventory_path= "vagrant_hosts"
        ansible.host_key_checking = false
      end 
  end
 
end
