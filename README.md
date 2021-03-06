## Automated ELK Stack Deployment

The files in this repository were used to configure the network depicted below.

![TODO: Update the path with the name of your diagram](C:\Users\jclar\Joe-Clark-Repository\Diagrams\ELK Diagram.png)

These files have been tested and used to generate a live ELK deployment on Azure. They can be used to either recreate the entire deployment pictured above. Alternatively, select portions of the __playbook___ file may be used to install only certain pieces of it, such as Filebeat.

  - _TODO: C:\Users\jclar\Joe-Clark-Repository\Ansible\install-elk.yml_

This document contains the following details:
- Description of the Topologu
- Access Policies
- ELK Configuration
  - Beats in Use
  - Machines Being Monitored
- How to Use the Ansible Build


### Description of the Topology

The main purpose of this network is to expose a load-balanced and monitored instance of DVWA, the D*mn Vulnerable Web Application.

Load balancing ensures that the application will be highly __efficient___, in addition to restricting __access___ to the network.
- _TODO: What aspect of security do load balancers protect? What is the advantage of a jump box?_

Integrating an ELK server allows users to easily monitor the vulnerable VMs for changes to the __logs___ and system __metrics___.
- _Filebeat monitors the system looking for any changes and when the changes took place?_
- _TODO: What does Metricbeat record?_

The configuration details of each machine may be found below.
_Note: Use the [Markdown Table Generator](http://www.tablesgenerator.com/markdown_tables) to add/remove values from the table_.

| Name     | Function   | IP Address | Operating System |
|----------|------------|------------|------------------|
| Jump Box | Gateway    | 10.0.0.4   | Linux            |
| Web-1    | Web Server | 10.0.0.5   | Linux            |
| Web-2    | Web Server | 10.0.0.6   | Linux            |
| Web-3    | Web Server | 10.0.0.7   | Linux            |
| Red-ELK  | Server     | 10.1.0.4   | Linux            |

### Access Policies

The machines on the internal network are not exposed to the public Internet. 

Only the __Jump Box___ machine can accept connections from the Internet. Access to this machine is only allowed from the following IP addresses:
- _TODO: 97.80.130.38_

Machines within the network can only be accessed by __Jump Box___.
- _TODO: Which machine did you allow to access your ELK VM? What was its IP address?  Jump Box machine via the 10.0.0.4 IP address._

A summary of the access policies in place can be found in the table below.

| Name     | Publicly Accessable | Allowed IP Address |
|----------|---------------------|--------------------|
| Jump Box | Yes                 | Home IP Address    |
| Web-1    | No                  | 10.0.0.4           |
| Web-2    | No                  | 10.0.0.4           |
| Web-3    | No                  | 10.0.0.4           |
| Red-ELK  | No                  | Home IP, 10.0.0.4  |

### Elk Configuration

Ansible was used to automate configuration of the ELK machine. No configuration was performed manually, which is advantageous because...
- _TODO: What is the main advantage of automating configuration with Ansible?  The advantage is you can automate the same actions accross the entire network and configure several PCs at the same time_

The playbook implements the following tasks:
- _TODO: In 3-5 bullets, explain the steps of the ELK installation play. E.g., install Docker; download image; etc._
- Install docker.io
- Install Python-pip
- Install docker container

The following screenshot displays the result of running `docker ps` after successfully configuring the ELK instance.

![TODO: Update the path with the name of your screenshot of docker ps output](C:\Users\jclar\Joe-Clark-Repository\Screenshots\docker_ps_output.png)

### Target Machines & Beats
This ELK server is configured to monitor the following machines:
- _TODO: List the IP addresses of the machines you are monitoring Web-1 (10.0.0.5) Web-2 (10.0.0.6) Web-3 (10.0.0.7)_

We have installed the following Beats on these machines:
- _TODO: Specify which Beats you successfully installed: Filebeat_

These Beats allow us to collect the following information from each machine:
- _TODO: In 1-2 sentences, explain what kind of data each beat collects, and provide 1 example of what you expect to see. E.g., `Winlogbeat` collects Windows logs, which we use to track user logon events, etc._
- Filebeat allows the collection of changes made and also lets us see when said changes were made.

### Using the Playbook
In order to use the playbook, you will need to have an Ansible control node already configured. Assuming you have such a control node provisioned: 

SSH into the control node and follow the steps below:
- Copy the __playbook_____ file to __ansible___.
- Update the __host___ file to include webservers and elk
- Run the playbook, and navigate to _Kibana web site___ to check that the installation worked as expected.

_TODO: Answer the following questions to fill in the blanks:_
- _Which file is the playbook? Where do you copy it?  install-elk.yml, copy to /etc/ansible/install-elk.yml_
- _Which file do you update to make Ansible run the playbook on a specific machine? _hosts_ How do I specify which machine to install the ELK server on versus which to install Filebeat on?_
- _Which URL do you navigate to in order to check that the ELK server is running?: http://ELK-VM.external.IP:5601/app/kibana

_As a **Bonus**, provide the specific commands the user will need to run to download the playbook, update the files, etc._