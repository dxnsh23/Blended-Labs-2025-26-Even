# Build Your VPC and Launch a Web Server (AWS) 

## Objective

The objective of this experiment is to understand how to design and configure a basic network infrastructure in AWS using a Virtual Private Cloud (VPC). This lab focuses on creating a VPC with a public subnet, configuring an Internet Gateway and route table, launching an EC2 instance, and hosting a simple web server that can be accessed over the internet.


## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* Web browser with internet connectivity


## Tools Used

* AWS Management Console
* Amazon VPC
* Amazon EC2
* Internet Gateway
* Route Table
* Security Groups


## Tasks Performed

### Task 1: Create a VPC

Create a new Virtual Private Cloud (VPC) with a private IP address range. The VPC acts as a logically isolated network in AWS where all other resources will be deployed.

Students should create a VPC with an appropriate CIDR block (for example, 10.0.0.0/16) and assign a meaningful name.

### Task 2: Create a Public Subnet

Create a subnet inside the VPC to host public resources. Enable auto-assign public IPv4 so that instances launched in this subnet receive a public IP address.

The subnet should use a smaller CIDR range (for example, 10.0.1.0/24).

### Task 3: Create and Attach Internet Gateway

Create an Internet Gateway (IGW) and attach it to the VPC. This allows communication between resources in the VPC and the internet.

### Task 4: Configure Route Table

Create a route table and add a default route (0.0.0.0/0) pointing to the Internet Gateway. Associate this route table with the public subnet.

This step ensures that traffic from the subnet can reach the internet.


### Task 5: Create Security Group

Create a security group to act as a virtual firewall for the EC2 instance. Configure inbound rules to allow:

SSH on port 22

HTTP on port 80


### Task 6: Launch EC2 Instance

Launch an EC2 instance inside the public subnet using Amazon Linux 2 AMI and a suitable instance type (t2.micro).

Attach the previously created security group and key pair.


### Task 7: Configure Web Server

Install and start a web server (Apache HTTPD) on the EC2 instance using user data or manual commands.

Create a simple HTML page and verify that it can be accessed from a web browser using the public IP address of the instance.---

## Workflow (Student Explanation)

1. Create a Virtual Private Cloud (VPC) with a CIDR block (e.g., 10.0.0.0/16) to establish a logically isolated network in AWS. This forms the foundation where all cloud resources will reside.
2. Create a public subnet (e.g., 10.0.1.0/24) inside the VPC and enable auto-assign public IP. This allows instances in the subnet to be accessible from the internet.
3. Create an Internet Gateway (IGW) and attach it to the VPC. Then configure a route table with a default route (0.0.0.0/0) pointing to the IGW and associate it with the public subnet to enable internet access.
4. Create a Security Group to act as a firewall. Allow inbound traffic for:

SSH (port 22) → for remote access

HTTP (port 80) → for web server access

5. Launch an EC2 instance (Amazon Linux 2, t2.micro) in the public subnet, attach the security group, and configure a web server (Apache). Deploy a simple HTML page and verify access using the instance’s public IP.


## Output Screenshots 

### Screenshot 1: VPC and Subnet Details

<img width="1914" height="913" alt="Screenshot 2026-02-24 105947" src="https://github.com/user-attachments/assets/0af1e33d-45ea-4bb1-8534-03e284d05dac" />


### Screenshot 2: EC2 Instance Running

<img width="1902" height="911" alt="Screenshot 2026-02-24 111106" src="https://github.com/user-attachments/assets/ee98e4b0-21b1-4eaf-a0b5-523bf008bfd4" />


### Screenshot 3: Web Server Output in Browser

<img width="1805" height="804" alt="Screenshot 2026-02-24 111144" src="https://github.com/user-attachments/assets/03f66c23-578e-4daa-8c60-d662e02fdcfb" />


## Result 

This experiment successfully demonstrated the creation of a custom VPC and deployment of a public-facing web server in AWS. By configuring networking components such as subnets, route tables, and security groups, and by launching an EC2 instance with a web server, the basic architecture of a cloud-hosted application was understood.
