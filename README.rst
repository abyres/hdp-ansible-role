This repository contains ansible roles for setting up HDP cluster

Coverage of this ansible role repository is to cover:

* setting up java in all nodes
* setting up SSH key in all nodes
* setting up ambari in a single ambari node
* setting up repository mirror

======================
First run modification
======================
* set up files/hosts.sample to include all hosts for mapping in /etc/hosts
* set up passwordless SSH using the bash script provided in files/
* make sure files/list_of_servers.txt is updated with proper IP and password 

===================
Available Roles (updated 13th December 2016)
===================

hdp25.ambari-prep
================

Purpose: Setup the basic requirements on a server before we install Ambari server 

Tasks:

* disable selinux
* reboot machine to disable selinux
* install new packages
* enable ntpd and disable firewall
* install hdp repository
* install ambari repository
* install oracle java 1.7
* setup oracle java as default system java
* install SSH key

hdp25.install-ambari
====================
Purpose: install ambari-server and run it

Tasks: 

* install ambari-server and run it
* copy ssh private key for master to worker nodes passwordless ssh. 

hdp25.post-installation
=======================
Purpose: setting up worker nodes 
Question: Why separate? Ans: Different requirements from master. No need too many
Tasks: 

* disable selinux
* install ntp
* restart workers VM
* disable firewall
* install java
* map hosts files
* install SSH

