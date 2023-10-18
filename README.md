# Ansible

Ansible is a software tool which enables you to have IaC (Infrastructure as Code) type of workflow <br/>to your cloud infrastructure. It allows you to provision, deploy and configure multiple resources at the execution of a yaml script.

In this repo, I have used Ansible to host two web servers that run Apache on Ubuntu virtual machine (EC2 Instances).<br/> I use Ansible on a master virtual machine (Ubuntu) that configures changes to the two servers.

<hr/>

<h2>Prereuisites:</h2>

In order to be able to make deployments to the web servers, you must have a SSH connection to your machines from the master server,<br/> where you will run Ansible commands.

The instances must allow SSH, therefore port 22 on the instances must be open.<br/> The method of connection (.pem or .ppk) does not matter, you may even use PuTTy SSH client,<br/>   
Since I'm on Ubuntu OS, I run the "ssh-keygen" on my master server

Once you have achieved the SSH connections to your machines. You must add the IP addresses of those machines into the<br/> ansible-HostsFile (found in my repo) that is created when installing Ansible 

On my master machine I run these commands (please refer to other documentation if you are not using Linux OS)
```
sudo apt install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```
