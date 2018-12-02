## What is Ansible ?

Ansible is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

- Ansible is Open Source
- Ansible is Agent less
- Ansible is Idempotent
- Ansible is Secure as it works over SSH
- Ansible is Simple

## Ansible Components

![Asnible Components](/docs/ansible-architecture.jpg)

## Ansible Demo Infrastructure 

![Demo Infrastructure](/docs/ansible-demo-server.jpg)

## Ansible Environment Setup - Instructions

- Install [VirtualBox](https://www.virtualbox.org/)
- Install [Vagrant](https://www.vagrantup.com/)
- Add VirtualBox install directory to system Path. (Example : C:\Program Files\Oracle\VirtualBox)
- Clone [this](https://github.com/schandan18/ansible-intro.git) Repository
- Open command prompt and cd into the directory for the above cloned Git Repository
- Set the HTTP Proxy (based on your site/network) ```set HTTPS_PROXY=http://<Proxy-Server-Name>:<Port-Number>```
- Execute Command ```vagrant up```
- Execute Command ```vboxmanage list runningvms``` the list running Virtual Machines
- Execute Command ```vagrant ssh acs``` to SSH into ACS VM 
  - Install Updates ```sudo apt-get update```
  - Install Ansible ```sudo apt-get install ansible```
  - Install sshpass ```sudo apt-get install sshpass```
  - Install git client ```sudo apt-get install git-core```
  - Clone [this](https://github.com/schandan18/ansible-intro.git) repository inside ACS VM
  - cd into ```ansible-intro/ansible``` directory
  - Execute command ```ssh vagrant@192.168.33.20``` accept defaults and logout
  - Execute command ```ssh vagrant@192.168.33.30``` accept defaults and logout
  - Execute command ```ansible-playbook web_db.yaml -k --check``` to execute the Playbook in Dryrun mode
  - Execute command ```ansible-playbook web_db.yaml -k``` to execute the Playbook
- Execute Command ```vagrant ssh web``` to SSH into WEB VM
- Execute Command ```vagrant ssh db``` to SSH into DB VM
