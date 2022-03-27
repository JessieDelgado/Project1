## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](Images/diagram_filename.png)

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

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

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

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the _____ file to _____.
- Update the _____ file to include...
- Run the playbook, and navigate to ____ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._