vagrant-plain
=============

This is a simple vagrant setup that will allow you to manually install packages and try out new configurations.

If you have never heard of vagrant checkout [Vagrant: What, Why and How][3]

##Getting Started


* [Download Virtual Box][2] and install it.
* [Download Vagrant][1] and install it.
* Clone this repo: `git clone https://github.com/anglinb/vagrant-plain`
* Move into that dir: `cd vagrant-plain`
* Run this command: `vagrant box add precise32 http://files.vagrantup.com/precise32.box`
* Run this command: `vagrant up`

Your virtual machine will a couple minutes to boot. 

####Shutting Down 
* `vagrant halt`

##Installing Packages

The virtual machine will headless therefore you must access it through ssh.

* Run `vagrant ssh`
* Run `sudo apt-get install <packagename>`

Run `vagrant ssh` to ssh into the virtual machine. If this doens't work run `ssh vagrant@localhost:2222` and login with `vagrant` as you username and password.

The system is running 32-bit Ubuntu so simply run `sudo apt-get <packagename>` to install a package.

To logout simply run `logout`.

##How it works

Vagrant reads all of it's configuration from the `Vagranfile`. This file contains a few standard configurations that are helpful for getting a server running. I encourage you to look at it. It has alot of comments that make it easier to understand.

* Port 8888 on your mahcine will forward to port 80 on the virutal machine.
* Port 2222 on your machine will forward to port 22 on the virutal machine.
* The directory `web_root` will be synced to `/var/www/web_root` on you virtual machine. User `www-data` will own it.


[1]:http://http://downloads.vagrantup.com/ "Vagrant Downloads"
[2]:https://www.virtualbox.org/wiki/Downloads "Virtual Box Downloads"
[3]:http://net.tutsplus.com/tutorials/php/vagrant-what-why-and-how/ "Vagrant: What, Why, and How"
