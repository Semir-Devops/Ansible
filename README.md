# Ansible

Ansible is a software tool which enables you to have IaC (Infrastructure as Code) type of workflow <br/>to your cloud infrastructure. It allows you to provision, deploy and configure multiple resources at the execution of a yaml script.

In this repo, I have used Ansible to host two web servers that run Apache on an Ubuntu virtual machine (EC2 Instances).<br/> I use Ansible on a master virtual machine that configures changes to the two servers.

<hr/>

<h2>Prereuisites:</h2>

In order to be able to make changes to the web servers, you must have a SSH connection to your machines from the master server,<br/> where you will run Ansible commands.

The instances must allow SSH, therefore port 22 on the instances must be open & the public key of the master machine must be added into the   

Once you have achieved the SSH connections to your machines. You must add the IP addresses of those machines into the ansible-HostsFile
