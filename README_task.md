# VM - Virtual Machine
bundle install- installs ruby dependencies

#### Provisions

shell 'provision' files are used to feed the software everything it needs at start up.

E.g. These are terminal commands that one would execute after initiating 'vagrant'. (written in the shell file)
```
sudo apt-get -y update

sudo apt-get -y install nginx

service nginx start

sudo apt-get -y install nodejs npm
```
Having the shell file and linking it using the following code below, would allow the code to automatically execute.
Must be written in Vagrantfile.
```
config.vm.provision "shell", path: "environment/provision.sh"
```
#### Rake Spec - tests assertions laid out in 'sample_spec.rb'
.rpsec - ruby inspect [testing framework]

#### Add folder to VM
This sends 'app' folder to VM & syncs connection both ways.
Must be written in Vagrantfile.
```
config.vm.synced_folder "app", "/app"
```

#### Access VM
This command gives access to VM and its folders

```bash
vagrant ssh
```


### Node App#
npm - node package manager
npm install - install packages for node
npm start -

### tests

unit tests vs integration tests

unit tests test one piece of code at a time (i.e. code written on top of machine)
integration tests test the entire machine (i.e. virtualbox)
