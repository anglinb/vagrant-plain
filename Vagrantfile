Vagrant.configure("2") do |config|

  # Every Vagrant virtual environment requires a box to build off of.
  # "precise32" is an Ubuntu 32bit box
  config.vm.box = "precise32"

  # Forward guest port 80 to host port 8888 and name mapping
  config.vm.network :forwarded_port, guest: 80, host: 8888
  

  # Setting up synced foleder                                #Setting owner
  config.vm.synced_folder "web_root/", "/var/www/web_root/", :owner => "www-data"
end
