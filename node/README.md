Role Name: Nodejs
=========

This nodejs role helps you to install nodejs, npm and nvm in Debian based systems.

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
---
# defaults file for node
node_version: "18"

This nodejs role consists of the variables in defaults/main.yml 
---

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing nodejs playbook
      hosts: all
      become: yes
  	roles:
  	- name: node
    	  tags:
     	  - node

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="node" play.yml







