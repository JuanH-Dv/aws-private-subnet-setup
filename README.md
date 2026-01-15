<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Creating a Private Subnet

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-networks-private)

**Author:** Juan Hernández  
**Email:** juanm.h.t@outlook.com

---

## Creating a Private Subnet

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-private_afe1fdbd)

---

## Introducing Today's Project!

### What is Amazon VPC?

Amazon VPC is a service that lets you create a private, isolated section of the AWS cloud. It is useful because it enables you to control your network configuration, enhance security, and manage traffic flow between resources. 

### How I used Amazon VPC in this project

In today's project, I used Amazon VPC to create a private subnet that is isolated from the internet. This allowed me to set up a secure environment for resources that do not require direct internet access.

### One thing I didn't expect in this project was...

One thing I didn't expect in this project is that setting the CIDR block of my private subnet to 10.0.1.0/24 would keep each range completely separate from the other.

### This project took me...

This project took me almost an hour.

---

## Private vs Public Subnets

Public subnets route traffic through an internet gateway to allow direct internet access for instances, while private subnets are isolated and only used for internal VPC communication.

Having private subnets are useful because they provide a secure and isolated environment for resources that do not need direct internet access. 

My private and public subnets cannot have the same IP address ranges. This is because overlapping IP ranges can cause routing conflicts and network instability. Each subnet must have a unique CIDR block to ensure proper communication.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-private_afe1fdbd)

---

## A dedicated route table

By default, my private subnet is associated with NextWork Public Route Table 

I had to set up a new route table because the default route table has a route to an internet gateway, and having that route would make my private subnet public.

My private subnet's dedicated route table only has one inbound and one outbound rule that allows to only direct traffic to another internal resource.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-private_b4b904b5)

---

## A new network ACL

By default, my private subnet is associated with the default ACL of my VPC.

I set up a dedicated network ACL for my private subnet because the default network ACL allows all traffic, which exposes my private subnet to unrestricted access from the internet or other untrusted networks.

My new network ACL has two simple rules, denying all inbound and outbound traffic, since it is a custom network ACL.

![Image](http://learn.nextwork.org/thoughtful_azure_glamorous_nectarine/uploads/aws-networks-private_1ed2cb07)

---

---

---
