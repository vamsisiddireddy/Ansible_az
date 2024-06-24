Role Name: CIS-Benchmark
=========

Image hardening in Linux enhances system security by reducing vulnerabilities and fortifying its resistance against potential attacks or compromises.

Hardware Requirements
---------------------
1. Ubuntu 22.04 or 20.04 Pro
2. 1vCPU
3. 1GB RAM
4. 8GB or more

Dependencies
------------
1.  Ansible 2.0 or higher installed on the control node. 
2.  Target hosts should be Debian-based systems. 
3.  Proper SSH access and authentication to target hosts. 
4.  Basic understanding of Ansible concepts such as playbooks, roles, and inventory.

Role Structure Overview
-----------------------
1.  Defaults: All variables are stored in defaults/main.yml.                                                   
2.  Tasks: Main tasks are defined in tasks/debian.yml     
3.  By importing tasks from tasks/debian.yml into tasks/main.yml, you can seamlessly integrate Debian-specific tasks into your playbook execution



Role Variables
--------------

This CIS-Benchmark has two types of compliance i.e., level1 and level2 and the variables in defaults/main.yml 

# defaults file for cis-benchmark
level_1: cis_level1_server
level_2: cis_level2_server

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing CIS-Benchmark playbook
      hosts: all
      become: yes
  	roles:
  	- name: cis-benchmark
    	  tags:
     	  - cis-benchmark

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="cis-benchmark" play.yml





