Role Name: Node Exporter
=========

This node exporter role helps you to install node exporter in Debian based systems and runs it as a service.

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
1.  Tasks: Main tasks are defined in tasks/debian.yml.   
2.  By importing tasks from tasks/debian.yml into tasks/main.yml, you can seamlessly integrate Debian-specific tasks into your playbook execution.
3.  Templates: Jinja template is placed under templates/node_exporter.j2 is used to run node exporter as a service.

Role Variables
--------------

This node exporter  role consists the variables in defaults/main.yml 
---
# defaults file for node_exporter
url: "https://github.com/prometheus/node_exporter/releases/download/v{{ version }}/node_exporter-1.5.0.linux-amd64.tar.gz"
version: 1.5.0

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing node exporter playbook
      hosts: all
      become: yes
  	roles:
  	- name: node_exporter
    	  tags:
     	  - node_exporter

Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="node_exporter" play.yml








