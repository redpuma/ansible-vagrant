
#
# Vagrantfile for DevOps Test
#

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  #config.vm.box = "hashicorp/precise64"
  config.vm.box = "ubuntu/trusty64"
  config.ssh.insert_key = false

  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 4
  end

  #
  # Ansible Hub (ans02.dev)
  #

  config.vm.define "ans02.dev" do |ans02|

    ans02.vm.hostname = "ans02.dev"
    ans02.vm.network :private_network, ip: "192.168.168.160"

    ans02.vm.provider :virtualbox do |v|
      v.name = "ans02.dev"
      v.memory = 1024
    end

     ans02.vm.provision :ansible do |ansible|
       ansible.playbook = "provisioning/ansible/ans02.yml"
       ansible.sudo = true
     end

     ans02.vm.synced_folder "./ansible/", "/usr/local/ansible"
  end


  #
  # Ubuntu (ubt01.dev)
  #

   config.vm.define "ubt01.dev" do |ubt01|

     ubt01.vm.hostname = "ubt01.dev"
     ubt01.vm.network :private_network, ip: "192.168.168.151"

     ubt01.vm.provider :virtualbox do |v|
       v.name = "ubt01.dev"
       v.memory = 2048
     end

     ubt01.vm.provision :ansible do |ansible|
       ansible.playbook = "provisioning/ansible/ubt01.yml"
       ansible.sudo = true
     end
   end

end
