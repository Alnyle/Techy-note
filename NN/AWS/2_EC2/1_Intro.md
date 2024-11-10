
• EC2 is one of the most popular of AWS’ offering 
• EC2 = Elastic Compute Cloud = Infrastructure as a Service
• It mainly consists in the capability of :
	• Renting virtual machines (EC2)
	• Storing data on virtual drives (EBS)
	• Distributing load across machines (ELB)
	• Scaling the services using an auto-scaling group (ASG)
• Knowing EC2 is fundamental to understand how the Cloud works

Choose in `EC2` instance :
 1. Operating System (OS): Linux, Windows or MAC OS
 2. How much compute power & cores (CPU)
 3. How RAM (random access memory)
 4. How much storage space: 
	 • Network-attached (EBS & EFS)
	 • hardware (EC2 Instance Store)
5. Network card: speed of the card, Public IP address 
6. Firewall rules: security group



##### Bootstrap script (configure at first launch): EC2 User Data

**bootstrap script** is a script that runs when an instance (such as an EC2 instance) first launches. Typically, this is used to set up the environment, install required software, and configure the instance to perform its intended role. AWS provides an easy way to pass this script to an EC2 instance through **User Data**.

Bootstrapping in AWS simply means to add commands or scripts to **AWS EC2’s instance User Data** section that can be executed when the instance starts. It is a good automation practice to adopt to ease configuration tasks.


### Key points about a bootstrap script:

- **User Data**: When launching an EC2 instance, you can pass a script or commands in the "User Data" field. This script is executed when the instance starts for the first time. This is commonly used for:
	- automation tasks like installing packages, pulling code from repositories, or configuring services.
    Installing updates
	• Installing software
	• Downloading common files from the internet

- **Script Format**: The script can be a bash script (for Linux instances) or a batch script (for Windows instances).

- **`The EC2 User Data Script runs with the root user`**


![[1_t5XthZnh0MZx7M3gqu-v-A.webp]]

https://medium.com/codex/bootstrapping-aws-ec2-instance-to-update-packages-install-and-start-apache-http-server-f68fe1fe33ba 
