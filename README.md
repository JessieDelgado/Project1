## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Project 1 drawio](https://user-images.githubusercontent.com/92039917/160265236-b7c2468a-1a7b-45dc-a46f-ae065f3a06c3.png)


These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the playbook file may be used to install only certain pieces of it, such as Filebeat.

  - DVWA
  - Elk
  - Filebeat
  - Metricbeat

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.

 -A load balancers are very important because they help prevent failure caused by overloading, specifically from DDOS attacks. They serve as a single point of accesss for multiple machines, and make sure they ensure high availability.

-The advantages of a having jump box is that it works as a point of contact for admin before jumping into the other machines. Inorder to access the other machines one must first be able to access the jump box.  

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the log files and system resources.

- Filebeat monitors the log files or location that someone specify. It will collect log events, and forwards them either to Elasticsearch for displayed.

- Metricbeat gathers the metrics and statistics. It'll then send that data to Elasticsearch to be displayed.

| Name     | Function                  | IP Address | Operating System |
|----------|---------------------------|------------|------------------|
| Jump Box | Gateway                   | 10.0.0.4   | Linux            |
| Web 1    | Web Server                | 10.0.0.5   | Linux            |
| Web 2    | Web Server                | 10.0.0.6   | Linux            |
| DVWA-VM  | Web Server                | 10.0.0.11  | Linux            |
| Elk-VM   | Web Server Elk Stack Host | 10.1.0.4   | Linux            |


### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- 98.53.250.107

Machines within the network can only be accessed by Jump Box VM.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?_
-Jump Box
-Public IP: 104.40.71.93 
-Private IP: 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name              | Publicly Accessible           |  Allowed IP Addresses |
|-------------------|-------------------------------|-----------------------|
| Jump Box          | Yes SSH, HTTP, TCP, Elk, 5601 | 98.52.250.107         |
| Web 1 Web 2 DVWM  | NO SSH, HTTP                  | 10.0.0.4              |
| ELK               | YES SSH, ELK, 5601            | 98.52.250.107         |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because Ansible help created a more uniform infrasture across different machines. 

The playbook implements the following tasks:
- Installed Docker to the Elk-VM
- Install Python3_pip
- Increased the Running VM memory
- Launched the docker into the VM

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

<img width="953" alt="project" src="https://user-images.githubusercontent.com/92039917/160264038-e3203b5a-613d-43fc-88dd-c465398fb554.png">


### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- Web 1
- Web 2
- DVWA-VM
- Jump Box 
- Elk-VM

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat 

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
-Filebeat gathers data about the file system. These files are then used to create logs
-Metricbeat gathers the metrics of the machines. This includes things such as attempted SSH logins, memory usage, uptime, CPU usage etc. 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the hosts file to include [elk] under [webservers]. Then the IP of the Elk-VM which was 10.1.0.4.
- Run the playbook, and navigate to http://[your_elk_server_ip]:5601/app/kibana to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

