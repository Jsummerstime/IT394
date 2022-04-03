# IT394 Project 2
# Created By Jack Summers

## Purpose:

The purpose of this project is to provide system administrators with a tool to automate the wagtail configuration process with ansible. 
Automating the task will allow users to spin up virtual machines at scale and configuring them into wagtail webservers. 
In turn, when an administrator is expecting or experiencing more web traffic, they can quickly increase the number of webservers to handle the traffic.

Wagtail is a content management system that provides a fast, aesthetic interface for users. It allows users to create blogs with images. 
Additionally, administrators have complete control over front end design and structure, but the system already works “out of the box”. 
Finally, Wagtail has a powerful search feature supported by PostgreSQL.

## Problem:

The Ansible Playbook solves the problem of decreasing configuration time. Additionally, the automated tool allows Wagtail webservers to be created at scale. 
Without the playbook, the cloud model in use would not follow all the main characteristics of a cloud model. 
Specifically, the playbook addresses the characteristic of rapid elasticity. When web traffic is low, then fewer virtual machines hosting wagtail 
webservers are required. However, if demand increases, then the playbook may be coupled with a second .yml file to spin up more virtual machines 
and configure them to be Wagtail webservers automatically.

## Getting Started:

### If your virtual machine is not configured to be a webserver follow these instructions first:

    sudo apt install git
    git clone https://github.com/do-community/ansible-playbooks.git
    cd ansible-playbooks/wordpress-lamp_ubuntu1804
Update the username and password variables in the vars directory:
    cd ansible-playbooks/vars
    nano default.yml
Edit the lines for mysql user and password to be what you want. Remember these for the next steps!
    mysql_user: "wordpressusername"
    mysql_password: "super-secret-password-goes-here"
Run the playbook
    ansible-playbook -u cadet playbook.yml --ask-become-pass

### If the above has already been configured, use the following commands to automatically configure a Wagtail blog:

    sudo apt install ansible
    sudo nano /etc/ansible/host
In / etc/ansible/host add the IP address of your VM.
    sudo apt install git
    git clone https://github.com/Jsummerstime/IT394/
    cd IT394
    ansible-playbook -u cadet playbook2.yml --ask-become-pass
