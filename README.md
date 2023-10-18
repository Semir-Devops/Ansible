# Ansible

Ansible is a software tool which enables you to have an IaC (Infrastructure as Code) type of workflow <br/>to your cloud infrastructure. It allows you to provision, deploy and configure multiple resources at the execution of a yaml script.

In this repo, I have used Ansible to host two web servers that run PHP-Apache2 on Ubuntu virtual machine (EC2 Instances).<br/> I use Ansible on a master virtual machine (Ubuntu) that configures changes to the two servers.

<hr/>

<h2>Prereuisites:</h2>

In order to be able to make deployments to the web servers, you must have a SSH connection to your machines from the master server, where you will run Ansible commands.

The instances must allow SSH, therefore port 22 on the instances must be open.<br/> The method of connection (.pem or .ppk) does not matter, you may even use PuTTy SSH client.<br/>   
Since I'm on Ubuntu OS, I run the "ssh-keygen" on my master server

<hr/>

Once you have achieved the SSH connections to your machines. You must add the IP addresses of those machines into the<br/> ansible-HostsFile (found in my repo) that is created when installing Ansible 

On my master machine I run these commands (please refer to other documentation if you are not using Linux OS):
```
sudo apt install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt update
sudo apt install ansible
```
<b>software-properties-common:</b> This software will help to manage ansible as a repository

These next commands are to be run on the host machines:

```
sudo apt update
sudo apt install python3
```
<hr/>

The next step will be to cofigure the hosts file within Ansible,<br/>If the installation went coorectly, you should find the file in ~/etc/ansible/hosts<br/>
edit this file to add your host machine IPs, it is recommended to group them like in my hostsFile.<br/>This will come in handy in the real-world
<hr/>
The next step is to ping to ansible hosts to verify ansible is working on the host machines, you may use the command:<br/>

```
sudo ansible -m ping all
```
<hr/>
The final step is to run the following command to make changes by creating an ansible-playbooks.yaml,<br/> which will install,enable and deploy Apache2, all on default port 80
<br/>

You must use the command (if in a different directory, type PATH to yml file): 

```
ansible-playbook <name-of-yaml-file>.yml
```

The Output:

<img width="526" alt="ans-playbook-yml" src="https://github.com/Semir-Devops/Ansible/assets/144611511/750f0ba6-8c60-4c2e-a5a8-f9b78f783bfa">
<hr/>

The two host machines running Apache Web server:

<img width="824" alt="ans-2-server" src="https://github.com/Semir-Devops/Ansible/assets/144611511/30303f84-661f-4068-b34c-d42ebc20dc55">

<hr/>

<img width="878" alt="ans-1-server" src="https://github.com/Semir-Devops/Ansible/assets/144611511/7690c190-0fc2-4a9f-a745-26f64b3faee9">


