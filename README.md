# Vagrant Ansible Centos 7 Alpine Docker NGINX


## Background

[Vagrant](https://www.vagrantup.com/) is used to provision the VM's. 
[Docker](https://www.docker.com/) is used to build and manage linux containers. 
[Ansible](http://www.ansible.com/) is used in environment configuration managemnent tasks..

This Vagrant profile uses Ansible provisioner to create a centos 7 VM in virtual box, then it uses Ansible to build the latest alpine nginx docker containers for a simple www web app stack, Docker-style:

  - `www`: NGINX web app on alpine docker container.
 

## Getting Started

This README file is inside a folder that contains a `Vagrantfile` (hereafter this folder shall be called the [vagrant_root]), which tells Vagrant how to set up your virtual machine in VirtualBox.

To use the vagrant file, you will need to have done the following:

  1. Download and Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
  2. Download and Install [Vagrant](https://www.vagrantup.com/downloads.html)
  3. Install [Ansible](http://docs.ansible.com/intro_installation.html)
  4. Open a shell prompt (Terminal app on a Mac) and cd into the folder containing the `Vagrantfile`
  
Once all of that is done, you can simply type in `vagrant up`, and Vagrant will create a new centos 7 VM, install the base box, and configure it.

Once the new VM is up and running (after `vagrant up` is complete and you're back at the command prompt), you can log into it via SSH if you'd like by typing in `vagrant ssh`. Otherwise, the next steps are below.

### Setting up your hosts file

You need to modify your host machine's hosts file (Mac/Linux: `/etc/hosts`; Windows: `%systemroot%\system32\drivers\etc\hosts`), adding the line below:

    192.168.55.55  dockertest.test

After that is configured, you could visit http://dockertest.test/ in a browser, and you'll see the test page.

## Author Information

Created in 2017 by [Chandru Balasubramaniam]
