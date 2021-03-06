# IT394 Project 2
### Created By Jack Summers

## Purpose:

The main purpose of this project was to become more familiar with Ansible. This project is to provide system administrators with a tool 
to automate the wagtail configuration process with Ansible. 
Automating the task will allow users to spin up virtual machines at scale and configuring them into Wagtail webservers. 
In turn, when an administrator is expecting or experiencing more web traffic, they can quickly increase the number of webservers to handle the traffic.

Wagtail is a content management system that provides a fast, aesthetic interface for users. It allows users to create blogs with images. 
Additionally, administrators have complete control over front end design and structure, but the system already works “out of the box”. 
Finally, Wagtail has a powerful search feature supported by PostgreSQL. Citations are commented out within the playbooks code.

## Problem:

The Ansible Playbook solves the problem of decreasing configuration time. Additionally, the automated tool allows Wagtail webservers to be created at scale. 
Without the playbook, the cloud model in use would not follow all the main characteristics of a cloud model. 
Specifically, the playbook addresses the characteristic of rapid elasticity. When web traffic is low, then fewer virtual machines hosting wagtail 
webservers are required. However, if demand increases, then the playbook may be coupled with a second .yml file to spin up more virtual machines 
and configure them to be Wagtail webservers automatically.

## Getting Started:

#### If your virtual machine is not configured to use Ansible, follow these steps:
The ansible config commands were obtained from Colonel Hamilton:

    sudo apt install openssh-server git
    ssh-keygen
    cd .ssh
    sftp username@IPADDRESS
    cd .ssh
    put id_rsa.pub authorized_keys
    quit
    
    sudo apt install ansible
    sudo nano /etc/ansible/host
    cd ~
In / etc/ansible/host, uncomment [webservers] and add the IP address of the VM you wish to configure into a Wagtail server below it.


#### If the above has already been configured, use the following commands to automatically configure a Wagtail blog:

    sudo apt install git
    git clone https://github.com/Jsummerstime/IT394/
    cd IT394
    ansible-playbook -u username playbook2.yml --ask-become-pass

Bibliography 

[1] vaibh, “wagtail/wagtail,” GitHub, Apr. 13, 2022. https://github.com/wagtail/wagtail/blob/main/README.md (accessed Apr. 13, 2022).
[2] “command – Execute commands on targets — Ansible Documentation,” docs.ansible.com. https://docs.ansible.com/ansible/2.9/modules/command_module.html (accessed Apr. 13, 2022).
[3] kaliko, “Run shell command from Ansible,” Unix & Linux Stack Exchange, 2019. https://unix.stackexchange.com/questions/515456/run-shell-command-from-ansible (accessed Apr. 13, 2022).
[4] pymen, “python - Not able to create super user with Django manage.py,” Stack Overflow, 2022. https://stackoverflow.com/questions/32532900/not-able-to-create-super-user-with-django-manage-py (accessed Apr. 13, 2022).
