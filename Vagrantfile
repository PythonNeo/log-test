VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "webserver" do |webserver| 
    webserver.vm.box = "debian/jessie64"
   # webserver.vm.hostname = "webserver"
    webserver.vm.provider "libvirt"
    webserver.vm.provision :shell, path: './python.sh' 
    webserver.vm.provision :ansible do |ansible|
     ansible.playbook = "playbook.yml"
    end
  end
  config.vm.define "logserver" do |logserver|
    logserver.vm.box = "debian/jessie64"
   # logserver.vm.hostname = "logserver"
    logserver.vm.provider "libvirt"
    logserver.vm.provision :ansible do |ansible|
     ansible.playbook = "playbook.yml"
    end
  end

end
