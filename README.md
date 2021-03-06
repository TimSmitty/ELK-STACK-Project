## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![Images/Azure Diagram.pdf]

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible file may be used to install only certain pieces of it, such as Filebeat.

  - ansibleplaybook.yml

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly secure, in addition to restricting traffic to the network.
- The load balancer helps protect against DDoS attacks. The jumpbox allows you to access any server incase one is down, you're still able to get to the others. 

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the _____ and system _____.
- Filebeat monitors the log files 
- Metricbeat records the metrics and statistics on your system

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web_1    |          | 10.0.0.5   | Linux            |
| Web_2    |          | 10.0.0.6   | Linux            |
| ELK      |          | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Whitelisted IP: 173.174.37.22
Machines within the network can only be accessed by the Jump Box.
- The Elk VM can be accessed through the Jump Box 10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | Yes                 | 173.174.37.22        |
| Web_1    | No                  | 10.0.0.4             |
| Web_2    | No                  | 10.0.0.4             |
| ELK      | No                  | 10.0.0.4             |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- Difficult manual tasks become repeatable and less vulnerable to error


The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![Images/docker ps.png]

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- 10.0.0.5, 10.0.0.6

We have installed the following Beats on these machines:
- Metricbeat, Filebeat

These Beats allow us to collect the following information from each machine:
- Filebeat was installed to monitor log files and collect log events. Metricbeat was installed to collect metrics and statistics 

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the Ansible host file to the Elk server.
- Update the playbook.yml file 
- Run the playbook, and navigate to your container and run 'sudo docker ps' to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? - playbook.yml 
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on? The ansibleplaybook.yml can be set to a certain IP address.
- _Which URL do you navigate to in order to check that the ELK server is running? Navigate to 
- 40.124.45.245:5601:app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._