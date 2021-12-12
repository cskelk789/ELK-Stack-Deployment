## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![ELK Server Implementation](https://user-images.githubusercontent.com/95726896/145699262-aac163ea-039e-48d3-bb53-b352aaa48a03.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the **yml and config** file may be used to install only certain pieces of it, such as Filebeat.

. [DVWA Web VM/Docker Configuration](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/DVWA/pentest.yml)
. [Hosts File](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/hosts)
. [Ansible Configuration](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/ansible.cfg)
. [ELK Installation and Configuration](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/ELK/install-elk.yml)
. [Filebeat Configuration](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/Filebeat/filebeat-config.yml)
. [Filebeat Playbook](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/Filebeat/filebeat-playbook.yml)
. [Metricbeat Configuration](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/Metricbeat/metricbeat-config.yml)
. [Metricbeat Playbook](https://github.com/cskelk789/ELK-Stack-Deployment/blob/main/Ansible/Metricbeat/metricbeat-playbook.yml)

This document contains the following details:
- Description of the Topology
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly **functional and available**, in addition to restricting **traffic** to the network.
- What aspect of security do load balancers protect? 

  ***Load balancers add resiliency by rerouting live traffic from one server to another if a server falls prey to a DDoS attack or otherwise becomes unavailable.\***

- What is the advantage of a jump box?

  ***A Jump Box Provisioner is also important as it prevents Azure VMs from being exposed via a public IP Address. This allows us to do monitoring and logging on a single box. We can also restrict the IP addresses able to communicate with the Jump Box, as we've done here.\***

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the **network** and system **logs**.
- What does Filebeat watch for?

  ***Filebeat monitors the log files or locations that you specify, collects log events, and forwards them either to Elasticsearch or Logstash for indexing.\***

- What does Metricbeat record?

  ***Metricbeat takes the metrics and statistics that it collects and ships them to the output that you specify, such as Elasticsearch or Logstash.\***

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name       | Function      | IP Address | Operating System |
| ---------- | ------------- | ---------- | ---------------- |
| Jump Box   | Gateway       | 10.0.0.1   | Linux            |
| Web-1      | Ubuntu Server |            | Linux            |
| Web-2      | Ubuntu Server |            | Linux            |
| Web-3      | Ubuntu Server |            | Linux            |
| ELK Server | Ubuntu Server |            | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __Jump-Box-Provisioner__ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:

- **_Workstation MY Public IP through TCP 5601_**

Machines within the network can only be accessed by __Workstation and Jump-Box-Provisioner through SSH JumpBox__.
- _Which machine did you allow to access your ELK VM? _
  - ***Jump-Box-Provisioner IP : 10.1.0.4 via SSH port 22\***

- _What was its IP address?_
  - ***Workstation MY Public IP via port TCP 5601\***


A summary of the access policies in place can be found in the table below.

| Name       | Publicly Accessible | Allowed IP Addresses |
| ---------- | ------------------- | -------------------- |
| Jump Box   | Yes                 | 10.0.0.1 10.0.0.2    |
| Web-1      | No                  |                      |
| Web-2      | No                  |                      |
| Web-3      | No                  |                      |
| ELK Server | No                  |                      |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _What is the main advantage of automating configuration with Ansible?_
  - ***There are multiple advantages, Ansible lets you quickly and easily deploy multitier applications through a YAML playbook.\***
  - ***You don't need to write custom code to automate your systems.\***
  - ***Ansible will also figure out how to get your systems to the state you want them to be in.\***

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- ...
- ...

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](Images/docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _List the IP addresses of the machines you are monitoring_
  - Web-1: 10.1.0.5
  - Web-2: 10.1.0.6
  - Web-3: 10.1.0.7


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
