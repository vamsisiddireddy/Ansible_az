Role Name: File Operation
=========

This File Operation role helps you to copy files from one location to another location in Debian based systems.

Hardware Requirements
---------------------
1. Ubuntu 22.04 or 20.04
2. 1vCPU
3. 1GB RAM
4. 8GB or more

Dependencies
------------
1.  Ansible 2.0 or higher installed on the control node. 
2.  Target hosts should be Debian-based systems. 
3.  Proper SSH access and authentication to target hosts. 
4.  Basic understanding of Ansible concepts such as playbooks, roles, and inventory.

Role Structure
--------------
1.  Defaults: All variables are stored in defaults/main.yml.                                                   
2.  Tasks: Main tasks are defined in tasks/debian.yml.   
3.  By importing tasks from tasks/debian.yml into tasks/main.yml, you can seamlessly integrate Debian-specific tasks into your playbook execution.

Role Variables
--------------

This file operation role consists of the variables in defaults/main.yml 
---
# defaults file for file operation
source_file_path: /home/ubuntu/oldfile
destination_file_path: /home/ubuntu/newfile

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing file operation playbook
      hosts: all
      become: yes
  	roles:
  	- name: fileoperation
    	  tags:
     	  - fileoperation

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="fileoperation" play.yml








