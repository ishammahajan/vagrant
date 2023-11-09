# Vagrant Resources
This repository provides Vagrant resources various projects.

## Getting Started
### Install Vagrant and VirtualBox
To install Vagrant on an Ubuntu 22.04 machine with VirtualBox as the provider, first add the VirtualBox repository to the apt sources list:
```
shell
sudo echo "deb [arch=amd64 signed-by=/usr/share/keyrings/oracle-virtualbox-2016.gpg] https://download.virtualbox.org/virtualbox/debian jammy contrib" >> /etc/apt/sources.list
wget -O- https://www.virtualbox.org/download/oracle_vbox_2016.asc | sudo gpg --dearmor --yes --output /usr/share/keyrings/oracle-virtualbox-2016.gpg
```
```
shell
sudo apt update
# Install VirtualBox
sudo apt install virtualbox-6.1
# For ChameleonCloud: Install generic linux headers for VirtualBox to provide hardware support for VMs
sudo apt install linux-headers-generic linux-headers-`uname -r`
sudo /sbin/vboxconfig
```

### Clone the repository
To clone this repository, use:
```shell
git clone https://github.com/purduecyan/vagrant.git
```

### Create the VMs
Navigate to the desired folder to create the necessary VMs. For example:
```shell
cd vagrant/kubernetes
```
Bring up the VMs using
```shell
vagrant up
```
Once the VMs are created, you can login to a VM using `vagrant ssh`. 
For example, after creating the kubernetes cluster, you can login to the master node using
```shell
vagrant ssh master
```
You can also stop all running VMs withing a project using 
```shell
vagrant halt
```

### Teardown
To delete all the VMs created, run
```shell
vagrant destroy
```

## Additional resources
You can find more information about Vagrant at https://www.vagrantup.com.
