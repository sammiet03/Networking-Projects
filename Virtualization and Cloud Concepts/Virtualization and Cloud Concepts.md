### Virtualization and Cloud Concepts

##### Virtualization 
-	Allows us to break one-to-one relationship of hardware to OS, allowing multiple OS’s to run on a single server
-	Each instance is a VM
-	A hypervisor is used to manage and allocated the hardware resources (another name is Virtual Machine Monitor (VMM))

##### Type 1 Hypervisor – used in data center environments 
-	Runs directly on top of the hardware
    -	Examples Microsoft Hyper-V
-	Also called bare-metal hypervisors because they run directly on the hardware (metal)
-	Another name native hypervisor 

##### Type 2 Hypervisor – common on personal devices 
-	Run as a program on an operating system like a regular computer program
    - Examples VMware, VirtualBox 
-	OS running directly on hardware = host OS
-	OS running in VM = guest OS
-	Another name hosted hypervisor 


### 3 Service Models of the Cloud 

##### Software as a Service (SaaS)
-	Provides customer to use providers applications running on a cloud infrastructure, consumer does not manage or control underlying cloud infrastructure 
-	Examples: Microsoft Office 365 
##### Platform as a Service (PaaS)
-	Provides customer to deploy onto the cloud infrastructure consumer created applications, consumer does not manage or control underlying cloud infrastructure, but has control over deployed applications and configuration settings for application-hosting environment 
##### Infrastructure as a Service (IaaS)
-	Consumer can provision processing, storage, networks, and other fundamental computing resources where customer is able to deploy and run arbitrary software, can include operating systems and applications.
-	Customers has limited control over OS, storage, deployed applications, and networking components 
### 4 Deployments Models of Cloud 
-	Private – single organization, large enterprises, can be on or off premises 
-	Community – used by specific community of consumer from organizations that have shared concerns
-	Public – for open use by public
-	Hybrid – composition of 2 or more distinct cloud infrastructures

##### 5 Characteristics of the Cloud
-	On-demand
-	Broad network access
-	Resource pooling
-	Rapid elasticity
-	Measure service 
