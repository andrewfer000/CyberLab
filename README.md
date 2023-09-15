# CyberLab (WIP)
A CyberSecurity and I.T. Learning Lab Framework utilising Flask, Python, Libvirt (QEMU), and Apache Guacamole. Desgined to be adopted and used by all

## Goals:
* User login and authentcation
  
* Labs are defined by code (JSON) which specifiy what VM disks to use, how many VMs of each, steps and stages, text questions, as well as deliverables and completion conditions. Labs are orginised in "courses"
  
* When a user starts a lab. They are given access to an interface with instructions and each VM in tabs. The GUI is powered by the Guacamole API
  
* Multiple Professors, Courses, and Students can use the system. Students can be enroled in courses by professors and students and professors can view progress 

* One instance, one server. Designed for simplicity for small and medium size deployments. (May change)

## System Requirements
* Server or reverse proxy with a public IP address for users to access the app
* Python 3.10+, Apache Guacamole, Libvirtd, QEMU with KVM acceleration
* 8 CPU cores with at least 16GB RAM per lab (4 VMs average)
* Network capible of many Quacamole users.

## Administrator Requirements
* Comprehensive understanding of Linux and Libvirt
* Baisc understanding and expreince with Apache Guacamole and Apache HTTPD
* Root privlages and permission to use a dedicated system and IP address. 

# No Code will be posted here until a working prototype is ready. Please be patient.
