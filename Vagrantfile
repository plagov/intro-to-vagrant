Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/precise64"
  config.vm.hostname = "web-dev"

  config.vm.provision "shell", path: "provision.sh"

  config.vm.network "forwarded_port", guest: 80, host: 8080, id: "nginx", auto_corrent: true

  # first, disable sharing of all content under project directory
  # then share explicity only two directories
  # first argument: location in host relative to Vagrantlike
  # second argument: absolute location in guest VM
  # disabled flag is set to false by default, unless is set otherwise
  config.vm.synced_folder "./", "/vagrant", disabled: true
  config.vm.synced_folder "www", "/vagrant/www"
  config.vm.synced_folder "sites-enabled", "/vagrant/sites-enabled"

end
