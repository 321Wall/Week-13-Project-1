## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![https://github.com/321Wall/Week-13-Project-1/blob/3bc4f0cd78723c66632a9810e370eb97b5784958/Diagrams/RedTeam%20-Elk%20Stack%20Diagram.pdf](Diagrams/RedTeam -Elk Stack Diagram.pdf)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the ansible playbook file may be used to install only certain pieces of it, such as Filebeat.

  - install-elk.yml [https://github.com/321Wall/Week-13-Project-1/blob/3bc4f0cd78723c66632a9810e370eb97b5784958/Ansible/Unit%2013%20Ansible%20Scripts.txt]

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly available, in addition to restricting access to the network.
- What aspect of security do load balancers protect? 
  Load balancers protect an organization against DDoS attacks by sending attack traffic from the corporate server to a public cloud provider.
- What is the advantage of a jump box?
  A jump box can be used by admins as a secure computer to first connect to before they launch a task or use a server to connect to other servers or untrusted environments.

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the data and system logs.
- What does Filebeat watch for?
  Filebeat monitors the log files, collects log events, locations, and sends them to Elasticsearch or Logstash for indexing.

- What does Metricbeat record?
  Metricbeats monitors your servers by collecting metrics you select from the system and services running on the server.

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function | IP Address | Operating System |
|----------|----------|------------|------------------|
| Jump Box | Gateway  | 10.0.0.4   | Linux            |
| Web1     |          | 10.0.0.5   | Linux            |
| Web2     |          | 10.0.0.6   | Linux            |
| Elk Stack|          | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the Jump Box machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- Add whitelisted IP addresses: Personal IP address, 10.1.0.4, and 10.0.0.4.

Machines within the network can only be accessed by SSH.
- Which machine did you allow to access your ELK VM? Jump-Box-Access
- What was its IP address? 20.12.206.3  10.0.0.4

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessible | Allowed IP Addresses |
|----------|---------------------|----------------------|
| Jump Box | No                  | Personal IP          |
| Web1     | No                  | 10.0.0.4             |
| Web2     | No                  | 10.0.0.4             |
| Elk-Stack| No                  | Personal IP, 10.0.0.4|
|          |                     |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- What is the main advantage of automating configuration with Ansible?
  Helps with the representation of Infrastructure as Code (IAC). This involves provisioning and management of the infrastructure and configuration through machine-processable definition lines.

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
- Install pip3
- Install docker module
- download and launch elk

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- List the IP addresses of the machines you are monitoring- 10.0.0.5 and 10.0.0.6

We have installed the following Beats on these machines:
- Filebeat and Metricbeat 

These Beats allow us to collect the following information from each machine:
- In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
Metricbeat helps you monitor your servers by collecting metrics from the system and services running on the server, such as: 
Apache module parses access and error logs created by the Apache HTTP server
System module collects and parses logs created by the system logging service of common Unix/Linux based distributions

Filebeat reads and forwards log lines and — if interrupted — remembers the location of where it left off when everything is back online.
Example for an Azure log is a platformlogs that provide detailed diagnostic and auditing information for Azure resources and the Azure platform they depend on.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the filebeat-config.yml file to your WebVM's.
- Update the filebeat-config.yml file to include...
- Run the playbook, and navigate to the Filebeat installation page on the ELK server GUI to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?_ filebeat-config.yml
- _Which file do you update to make Ansible run the playbook on a specific machine? How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?  http://[your.VM.IP]:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._
https://github.com/321Wall/Week-13-Project-1/blob/3bc4f0cd78723c66632a9810e370eb97b5784958/Ansible/Unit%2013%20Ansible%20Scripts.txt
