Role Name: Tomcat
=========

This Tomcat role helps you to install java and tomcat on Debian based systems.

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
4.  Templates: Jinja template is placed under templates/service.j2 and it is used to run as a service.
5.  Handlers:  Handlers in Ansible are actions triggered by tasks, often used for tasks like restarting services. 

Role Variables
--------------

---
# defaults file for tomcat
url: "https://dlcdn.apache.org/tomcat/tomcat-9/v{{ version }}/bin/apache-tomcat-{{ version }}.tar.gz"
version: 9.0.86

Playbook
--------

All the roles are written in the play.yml file by using specific tags so that we can install required roles on the target machine by using the following playbook:
    - name: Executing tomcat playbook
      hosts: all
      become: yes
  	roles:
  	- name: tomcat
    	  tags:
     	  - tomcat




Execution
---------

Run the above playbook using the ansible-playbook command 
$ ansible-playbook --tags="tomcat" play.yml








