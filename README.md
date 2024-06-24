# Ansible Project: MVP 

 This Ansible project consists of multiple roles designed to automate various tasks on Debian-based systems. 

# Getting Started:
# Table of Contents 

1.	Prerequisites 
2.	Installation 
3.	Usage 
4.	Roles 

# Prerequisites 

1.  Ansible 2.0 or higher installed on the control node. 
2.  Target hosts should be Debian-based systems. 
3.  Proper SSH access and authentication to target hosts. 
4.  Basic understanding of Ansible concepts such as playbooks, roles, and inventory. 
 

# Installation 

To install this Ansible Roles, follow these steps:

Clone the repository to your local machine: 
 - $ git clone https://dev.azure.com/devops-internal/mvp/_git/ansible 

Navigate to the project directory: 
 - $ cd ansible

# Usage

This Ansible project provides automation for various tasks on Debian-based systems. To use it: 
1.  Define your inventory file containing the target hosts i.e on /etc/ansible/hosts 
2.  Write your playbook, referencing the roles provided in this project i.e play.yml 
3.  Run the playbook using the ansible-playbook command 
    - $ ansible-playbook --tags="<provide specific role>" play.yml 

# Roles:
# Example:

Role : [Apache Tomcat] 
1.  Description: installation of Apache Tomcat and run it as a service   
2.  Defaults: All variables are stored in defaults/main.yml.                                                   
3.  Tasks: Main tasks are defined in tasks/debian.yml     
4.  Importing tasks from tasks/debian.yml into tasks/main.yml, you can easily include Debian-specific tasks as part of your playbook execution 
