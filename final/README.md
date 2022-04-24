# IT392 Final Project
### Created By Jack Summers and Ben Wettstein

## Purpose:
The purpose of this project is to utilize Ansible to automate system administrator tasks. The ansible script will automatically set up a Shuup E-Commerce site with a MySQL database. Both the E-commerce website and MySQL database are in seperate docker containers. 

This project's hypothetical situtation involves selling rings to the USMA class of 2023. Tiffany & Co. requires a website to sell their rings to cadets. This github provides the instructions to manually configure the E-commerce site and its database. 

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
    ansible-playbook -u username presta_playbook.yml --ask-become-pass
    
  ### Bibliography
    
[1] mhz, “Docker setup for Django on MySQL,” Medium, Nov. 16, 2018. https://medium.com/@minghz42/docker-setup-for-django-on-mysql-1f063c9d16a0 (accessed Apr.   20, 2022).

[2] olmerg, “Error in docker · Issue #2599 · shuup/shuup,” GitHub, 2021. https://github.com/shuup/shuup/issues/2599 (accessed Apr. 20, 2022).
    
[3] valan, “python - How to change MarkUpSafe version in virtual environment?,” Stack Overflow, 2022. https://stackoverflow.com/questions/71271759/how-to-change-markupsafe-version-in-virtual-environment (accessed Apr. 20, 2022).
    
[4] S. Paul, “Run DB migration script in docker-compose,” Medium, Apr. 21, 2018. https://medium.com/@sumankpaul/run-db-migration-script-in-docker-compose-ce8e447a77ba (accessed Apr. 20, 2022).
    
[5] “shuup/shuup,” GitHub, Apr. 20, 2022. https://github.com/shuup/shuup (accessed Apr. 20, 2022).
