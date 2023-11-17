# CyberLab (WIP)
CyberLab automates the management of Apache Guacamole and Libvirt QEMU Virtual Machines & Networks for use in temporary lab environments. Labs are defined in JSON files in their respective courses. Lab environments are very customisable. When you run a lab it creates a new "session". A session is made of a JSON file which tracks what resources (VMs, Networks, Guacamole User/Connections) is owned by that session. Sessions can be paused, resumed, and destoryed. A Lab interface HTML file is provided in each session's directory in ./session/session_id. 

## Goals:
* User login and authentcation
  
* Labs are defined by code (JSON) which specifiy what VM disks to use, how many VMs of each, steps and stages, text questions, as well as deliverables and completion conditions. Labs are orginised in "courses"

* Multiple checkers in python such as a "Linux file checker" or "Windows file checker" defined as Python using WinRM, SSH, PowerShell, and Python Scipts to check lab completion. 

* When a user starts a lab. They are given access to an interface with instructions and each VM in tabs. The GUI is powered by the Guacamole API
  
* Multiple Professors, Courses, and Students can use the system. Students can be enroled in courses by professors and students and professors can view progress 

* One instance, one server. Designed for simplicity for small and medium size deployments. (May change)

## System Requirements
* Server or reverse proxy with a public IP address for users to access the app
* Python 3.10+, Apache Guacamole, Libvirtd, QEMU with KVM acceleration
* 8 CPU cores with at least 16GB RAM per lab (4 VMs average)
* Network capible of many Guacamole users.

## Administrator Requirements
* Comprehensive understanding of Linux and Libvirt
* Baisc understanding and expreince with Apache Guacamole and Apache HTTPD
* Root privlages and permission to use a dedicated system and IP address.


## Benifits
**NOTE:** This benifits section applies to the FINISHED PRODUCT which does not exist yet

### For Trade Schools and Universities
1. Free and Open Source Software. Use and modify to your hearts content.
2. Deploy on your own systems. Keep your data safe.
3. Instructors and Administrators have full control.
4. Low cost to operate. All involved software is Free and Open Source. (Linux, (Apache/Nginx), Python, MySQL, Apache Guacamole, Libvirt/QEMU/KVM)
5. Web based access. No special software or user configurations required. Works with Firefox and Chromium based browsers. (Will likley work with any browser that can support HTML5, iframes, and HTMX)
6. LMS intergration (Far goal).
7. Scales to your needs. Deploy the backend (QEMU/KVM, MySQL, Apache Guacamole) on as many servers as you need. 
8. Secure and isolated. VMs and Networks are randomiszed and destoryed if inactive or lab is complete
9. Lab Session tracking is saved allowing for auditing. 
10. Paid Support, SLAs, and Whitelabeling Services will become available

### For Instructors and Lab Desginers
1. Design and Build Labs using your own VM images and use JSON code to design your lab. It's YOUR VMs, YOUR curriculum, YOUR labs. 
2. Reproducable Lab Environments. Same lab and results with every run.
3. Add Questions and "Checkers" to your labs for automatic grading. 
4. No setup for students. Once your course and labs are deployed. Enrolled students just click and run.
5. Courses based on popular curriculums will be made available for purchace in the future. Buy, Deploy, Run.
6. See student's progress. 

### For Students
1. Login, Click lab, and Learn! No setup required.
2. No powerful system required. Complete your labs on a chromebook!
3. Complete your labs from anywhere, any time! No need to spend time in a physical lab! 
4. No longer need to buy costly access to online lab simulators to complete your work. (Unless your university charges)
5. Mess up? Just reset and try again. Exam prep? Re-run labs to drill in those concepts! 

## Completion

### What is complete
1. Automatic Guacamole Management
2. Automatic QEMU and Network Management
3. Session creation and tracking
4. Session Lab Interface generation
5. Session pausing
6. Session resume
7. Session destory
8. Generate Lab Interface with instrustions and questions (Features still being added)

### What is incomplete
1. Lab JSON checking and validaton (Be careful when writing your own)
2. Lab Checkers
3. Web UI

## Install

* Frontend-  Follow the installation instructions here (not available)
* Daemon- Follow the installation instructtions here https://github.com/andrewfer000/CyberLab-Daemon


## Downloading the TestCourse
As of now the testcourse is recomended to use instead of starting from scrach. Download and extract the testlab/ folder into the courses directory. Feel free to modify it to your needs. If you copy the lab and create a file (say, testlab2.json) or change the name of the course be sure to change it in the `cyberlab_concept.py` file

TestCourse Download: https://drive.google.com/file/d/1jIKv6ErvM6-PKTilCNFpg7h0KEF6dIJe/view?usp=sharing

**NOTE:** Due to the large file size this zip only gets updated every once and awhile and changes to the lab system does change. Please refer to the References directory and use the example lab for the latest changes. For example, "disk" for disk type has been changed to windisk for Windows and lindisk for Linux for compatability reasons. 

## Running
### Information
Labs are part of courses. Courses contain vm_images directory (virtual hard drives and isos used for your labs) and a labs directory. If you download the testcourse and unzip it into the courses directory and run the new session command the lab should run without issues. As long as testcourse and it's files (testcourse/vm_images/myvm.qcow2, testcourse/vm_images/test.iso, testcourse/labs/testlab.json) are in-tact you can run the lab.

## Screenshots

#### Creating a session from the lab
![image](https://github.com/andrewfer000/CyberLab-Concept/assets/9620913/7c2b3fc9-ea33-4779-99d5-25c05dc609b4)

#### Directories and Files in the session's folder
![image](https://github.com/andrewfer000/CyberLab-Concept/assets/9620913/353b2f65-18d6-4871-85f0-4695053064ce)

#### Lab Interface
![image](https://github.com/andrewfer000/CyberLab-Concept/assets/9620913/82f633e6-a909-47e3-86cd-848fdae7725a)

#### Session File Snipit
![image](https://github.com/andrewfer000/CyberLab-Concept/assets/9620913/a2afb779-db58-4262-a2b0-bdf171891255)

#### Destory the session
![image](https://github.com/andrewfer000/CyberLab-Concept/assets/9620913/2dec8b5f-995c-474a-b507-ddf138914a00)

#### Sneek peek of when the Frontend and backend work toghether. CyberLab Simulator being accessed on a Smartphone!
![image](https://github.com/andrewfer000/CyberLab-Daemon/assets/9620913/fe556fd3-2a85-427c-9d06-b84a2e08334a)

## Other Details
* License: MPL 2.0 (Unless otherwise stated in source files)
* Please send me a message for any secuirty issues. 


# No Code will be posted here until a working prototype is ready. Please be patient.
