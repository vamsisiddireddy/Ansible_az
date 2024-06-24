Role Name: PHP
=========

This php role helps you to install required version of php on Debian based system and perform version management system.

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

This php role consists the variables in defaults/main.yml 
---
# defaults file for php
req_version: "7.4"

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing php playbook
      hosts: all
      become: yes
  	roles:
  	- name: php
    	  tags:
     	  - php

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="php" play.yml








