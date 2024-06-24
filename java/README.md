Role Name: Java
=========

This java role helps you to install the java with required version and switch to required version.

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

This Java has two variables in defaults/main.yml 
---
# defaults file for languages
version: 11

Playbook
--------
All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing java playbook
      hosts: all
      become: yes
  	roles:
  	- name: java
    	  tags:
     	  - java

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="java" play.yml









