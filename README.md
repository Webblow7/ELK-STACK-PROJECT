## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

**Note**: The following image link needs to be updated. Replace `diagram_filename.png` with the name of your diagram image file.  

[Elk-stack-Diagram](Diagram/ELKSTACKD.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the install_elk.yaml file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: Enter the playbook file._

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting inbound access to the network.


Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the filesystem and system metrics.


The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

+-------------+---------------------+----------------------+
| Name        | Publicly Accessible | Allowed IP Addresses |
+-------------+---------------------+----------------------+
| Jump Box    | Yes                 | Local Host           |
+-------------+---------------------+----------------------+
| WEB1        | No                  | 10.0.0.6             |
+-------------+---------------------+----------------------+
| WEB2        | No                  | 10.0.0.6             |
+-------------+---------------------+----------------------+
| ELK MONSTER | No                  | 10.1.0.4             |
+-------------+---------------------+----------------------+

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the jumpbox machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:


Machines within the network can only be accessed by each other. The WEB1,WEB2 VMS communicate and send traffic to the Jumpbox.


A summary of the access policies in place can be found in the table below.

+-------------+---------------------+----------------------+
| Name        | Publicly Accessible | Allowed IP Addresses |
+-------------+---------------------+----------------------+
| Jump Box    | Yes                 | Local Host           |
+-------------+---------------------+----------------------+
| WEB1        | No                  | 10.0.0.6             |
+-------------+---------------------+----------------------+
| WEB2        | No                  | 10.0.0.6             |
+-------------+---------------------+----------------------+
| ELK MONSTER | No                  | 10.1.0.4             |
+-------------+---------------------+----------------------+
### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because it makes the deployment more efficent.


The playbook implements the following tasks:
-Install docker
-Install Python 3 
-increase sytem memory
-download image and install Elk

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

**Note**: The following image link needs to be updated. Replace `docker_ps_output.png` with the name of your screenshot image file.  


![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- WEB1 10.0.0.5
- WEB2 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat
- Metricbeat

These Beats allow us to collect the following information from each machine:
-Filebeat collects log events and detects changes in the filesystem in addition ships the logs to a minitoring clusters.
-Metricbeat collects metrics from the operating system CPU usage and also can be used to monitor other beats and Elk stacks.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the configuration file to ansible.
- Update the host file to include the private address
- Run the playbook, and navigate to https://10.1.0.4 to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
