## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.



These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the install-elk.yml file may be used to install only certain pieces of it, such as Filebeat.


This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the Vulnerable Web Application.

Load balancing ensures that the application will be highly defensive against distributed denial-of-service (DDoS) attacks, in addition to restricting IP address communcation to the network.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the logs, system metrics and statistics.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
|Jump Box  | Gateway  | 10.0.0.4   | Linux            |
|ELK       |          | 10.2.0.4   | Linux            |
|WEB SERVER|          | 10.0.0.5   |                  |
|WEBSERVER2|          | 10.0.0.6   |                  |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the JumpBox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses: 174.245.66.19

Machines within the network can only be accessed by 10.0.0.5 10.0.0.6 


A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box |    Yes              |  174.245.66.19       |
|          |                     |                      |
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it helps to configure systems as well as deploy software.

The playbook implements the following tasks:

 Install docker.io this step installs the docker io
 Install python3-pip 
 the command module and the system module is specified
 download and launch a docker elk container by its name and image and the published ports
 Enable service docker on boot-      

- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

ELk_Stack_Project/Images/filepath.PNG

### Target Machines & Beats
This ELK server is configured to monitor the following machines: 10.0.0.5 10.0.0.6


We have installed the following Beats on these machines: filebeat which can collect audit logs.


These Beats allow us to collect the following information from the machine; audit log which has records providing information about who has accessed the system and what operations were performed during a given period of time.
They are useful both for maintaining security and for recovering lost transactions


### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the install-elk.yml file to /etc/ansible.
- Update the install-elk.yml file to include the specified configurations
- Run the playbook, and navigate to SSH into the ELK server and ensure that the sebp/elk:761 container is running, by running: docker ps. 

