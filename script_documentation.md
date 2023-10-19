explaining the script:
This script is for setting up virtual machines using Vagrant with two machines,
 one named "slave_1" and the other named "master." These virtual machines are 
 based on the "ubuntu/focal64" box and have some configuration and provisioning
 tasks.

must have: 
- vagrant
- virtualbox

Set up VirtualBox-specific settings for both the slave and the master:
Allocate 1024 MB of memory and 2 CPUs.

vagrant init ubuntu/focal64:
Initialize a new Vagrant environment using the "ubuntu/focal64" box.

Create a Vagrant configuration file called "Vagrantfile" with the following settings:

config.vm.define "slave_1": Define a virtual machine named "slave_1."

Inside the "slave_1" configuration:
Set the hostname of the virtual machine to "slave-1."
Use the "ubuntu/focal64" box.
Create a private network interface with IP address "192.168.18.11."

Provision the virtual machine with a series of shell commands:
Update and upgrade packages.
Install the "sshpass" tool.
Allow password authentication for SSH.
Restart the SSH service.
Install "avahi-daemon" and "libnss-mdns."

config.vm.define "master": Define another virtual machine named "master."

Inside the "master" configuration:
Set the hostname of the virtual machine to "master."
Use the "ubuntu/focal64" box.
Create a private network interface with IP address "192.168.18.10."


Provision the virtual machine with a series of shell commands:
Update and upgrade packages.
Install the "sshpass" tool.
Allow password authentication for SSH.
Restart the SSH service.
Install "avahi-daemon" and "libnss-mdns."

script configuration for masters:
creating a sudo user called "altschool"
create an ssh key for the user "altschool"
copy the user "altschool" ssh key to slave machine
copy a file named "/mnt" from the altschool user to the slave machine

Setting up a LAMP Stack:

Working with the "master" virtual machine to set up a LAMP stack (Linux, Apache, MySQL, and PHP):

 update the package manager's list of available software and apply any updates.
 install the Apache2 web server.
 configure the firewall to allow traffic for Apache.
 install the MySQL database server. 
 set proper permissions for the web directory.
 install PHP and some PHP-related modules.
 enable some Apache modules and configure the default web page.
 restart the Apache web server to apply the changes.
The LAMP stack is now installed and configured on the "master" virtual machine.

Working with the "slave_1" virtual machine to set up a LAMP stack (Linux, Apache, MySQL, and PHP):

update the package manager's list of available software and apply any updates.
 install the Apache2 web server.
 configure the firewall to allow traffic for Apache.
 install the MySQL database server. 
 set proper permissions for the web directory.
 install PHP and some PHP-related modules.
 enable some Apache modules and configure the default web page.
 restart the Apache web server to apply the changes.
The LAMP stack is now installed and configured on the "slave_1" virtual machine.