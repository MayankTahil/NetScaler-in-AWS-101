# Introduction to AWS and NetScaler
In this tutorial, we will explore the basics of AWS when provisioning:

1. Networking resources
2. Compute resources
3. Storage Resources. 

After learning the basics and configuring pre-requisite networking, we will then [deploy NetScaler ADC in AWS](https://www.youtube.com/watch?v=NvncDbmzgnY) to show how you can Load Balance a simple Website hosted on an EC2 instance via the NetScaler ADC. 


As a pre-requisite for this tutorial, please sign up and create your own AWS Free Tier account from the [sign in page](https://console.aws.amazon.com/console/home)

# Table of Contents

### [Networking in AWS (VPC)](VPC/)
1. Creating a VPC
2. Creating Three Subnets
  * Management Subnet
  * Server Subnet
  * Client Subnet
3. Creating Three Route Tables
  * Configure the MGMT Subnet Default Route Table
  * Create and Configure the Server Subnet's Route Table
  * Create and Configure the Client Subnet's Route Table
4. Summary of [Network Topolgy after completion](VPC/images/Base-NTW-Topology.jpg)

### [Computing in AWS (EC2)](EC2/)
1. Launch an Windows EC2 Instance (Client Network)
  * Launch EC2 Instance Wizard
  * Allocate an Elastic IP (EIP)
  * RDP into Windows EC2 Instance
2. Launch a Linux EC2 Instance (Server Network)
  * Launch EC2 Instance Wizard
  * SSH into Linux EC2 Instance
  * Host Two Webservers on port 80, 81, 82
  * Configure Custom Security Groups Rules
3. Summary of [Netowrk Topology after completion](EC2/images/Base-NTW-Topology.jpg)
  