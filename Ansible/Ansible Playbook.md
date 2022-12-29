## How to create an Ansible Playbook 


##### What is Ansible?
- Ansible is an open-source automation framework, owned and maintained by Red Hat.
- It can be used to provision the underlying infrastructure of your environment, virtualized hosts and hypervisors, network devices, and bare metal servers.
- It can also be used to install services, add compute hosts, and provision resources, services, and applications inside of your cloud. 

##### How Ansible Works
- There are 2 categories of computers: the control node and managed nodes
- The control node is a computer that runs Ansible. 
- The managed node is any device being managed by the control node.
- Ansible works by connecting to nodes on a network and then sending a small program called an Ansible module to that node. Ansible will execute these modules over SSH and removes them when finished. 
- Only requirement is that your Ansible control node has login access to the managed nodes, SSH is the most common way to provide access, but there are other forms of authentication that are supported. 

##### What is an Ansible Playbook?
- Modules provide the means of accomplishing a task, the way you use them is through an Ansible Playbook.
- A playbook is where you will construct all of the automation tasks. It is a configuration file written in YAML that provides instructions for what needs to be done in order to bring a managed node into the desired state.

#### Steps
- For this project, I will be using WSL to run Linux on my Windows computer since Ansible cannot run on Windows OS. 
- You want to open up PowerShell on your Windows computer and run as administrator.
- Then enter the "wsl --install" command, Ubuntu is the default Linux distribution that will be installed. If you would like to install a different version then follow the documentation below. 
- [Here is the documentation I used to download WSL on my Windows computer](https://learn.microsoft.com/en-us/windows/wsl/install)
