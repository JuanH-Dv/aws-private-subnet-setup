<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Launching VPC Resources

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-ec2)

**Author:** Juan Hernández 
**Email:** juanm.h.t@outlook.com

---

## Launching VPC Resources

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-ec2_8ee57662)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a virtual private cloud that lets users launch AWS resources in a logically isolated network. It is useful because it provides enhanced security, control over network configuration, and the ability to define custom routing and subnet structures.

### How I used Amazon VPC in this project

I used Amazon VPC to create a secure and isolated network environment for my resources. I set up public and private subnets, configured route tables, and used a resource map to visualize the network layout. 

### One thing I didn't expect in this project was...

One thing I didn't expect in this project was that there exists a faster and easier option to create VPCs.

### This project took me...

This project took me about 2 hours to complete.

---

## Setting Up Direct VM Access

Directly accessing a virtual machine means connecting to it through its network interface, typically via SSH, using a key pair or password authentication. 

### SSH is a key method for directly accessing a VM

SSH traffic means secure data transmission between a user's local machine and a remote server

### To enable direct access, I set up key pairs

Key pairs are sets of cryptographic keys used for secure authentication and encryption in computing. They consist of a public key and a private key, where the public key is shared and the private key is kept secret.

A private key's file format means the specific type of encoding or structure used to store the cryptographic key, such as PEM or PPK. My private key's file format was PEM, which is a common format for storing SSL/TLS certificates and keys.

---

## Launching a public server

I had to change my EC2 instance's networking settings by navigating to the network settings panel in the EC2 config page and selecting Edit at the right-hand corner.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-ec2_88727bef)

---

## Launching a private server

My private server has its own dedicated security group because it requires stricter access controls to ensure that only authorized traffic can reach it. 

My private server's security group's source is NextWork Public Security Group which means only resources that are part of the NextWork Public Security Group can communicate with my instance.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-ec2_4a9e8014)

---

## Speeding up VPC creation

I used an alternative way to set up an Amazon VPC! This time, I selected the "VPC and more" option instead of "VPC only" when creating the VPC. This brought up a VPC resource map, which is a visual flow diagram showing all the VPC resources being created on the same page. The resource map allowed me to see and configure subnets, route tables, internet gateways, and other components all at once, without having to jump between different pages in the VPC console.

A VPC resource map is a visual flow diagram that shows the architectural layout of a VPC, including subnets, route tables, internet gateways, and other resources. It helps users quickly understand how components are connected and interact.

My new VPC has a CIDR block of 10.0.0.0/16. It is possible for my new VPC to have the same IPv4 CIDR block as my existing VPC because AWS VPCs are isolated from each other by default, so there won’t be any IP conflicts unless I explicitly connect them using VPC peering.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-ec2_1cbb1b88)

---

## Speeding up VPC creation

### Tips for using the VPC resource map

When determining the number of public subnets in my VPC, I only had two options: 0 or 2. This was because AWS' best practice advice ensures that if I select 2 Availability Zones, the wizard makes sure I have a public subnet in each one, providing redundancy and high availability.

The set up page also offered to create NAT gateways, which are services that allow instances in private subnets to access the internet for updates and patches while blocking inbound traffic.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-ec2_8ee57662)

---

---

---
