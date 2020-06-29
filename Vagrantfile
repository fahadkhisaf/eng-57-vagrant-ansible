# Install required plugins
required_plugins = ["vagrant-hostsupdater"]
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
end

Vagrant.configure("2") do |config|
  config.vm.define "app" do |app|
    app.vm.box = "ubuntu/bionic64"
    app.vm.network "private_network", ip: "192.168.10.100"
    app.hostsupdater.aliases = ["development.local"]
    
    # synce folder
    app.vm.synced_folder "app", "/home/ubuntu/app"

    
    # Installing ansible 
    app.vm.provision "ansible_local" do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
end
# # Install required plugins
# required_plugins = ["vagrant-hostsupdater"]
# required_plugins.each do |plugin|
#     exec "vagrant plugin install #{plugin}" unless Vagrant.has_plugin? plugin
# end
# Vagrant.configure("2") do |config|

#   config.vm.box = "ubuntu/xenial64"
#   config.vm.network "private_network", ip: "192.168.10.100"
#   config.vm.hostname = 'ansible_nodejs'
#   config.hostsupdater.aliases = ["development.local"]


#   # synced folder -- connection both ways
#   # config.vm.synced_folder("path in origin folder to sync", "path in machine folder to sync")
#   config.vm.synced_folder "app", "/app"

#   config.vm.provision "shell", path: "environment/provision.sh"

#   #installing and running ansible
#   config.vm.provision "ansible" do |ansible|
#     ansible.playbook = "playbook.yml"
#   end
# end
