# Introduction to AWS and NetScaler
In this tutorial, we will explore the basics of AWS when provisioning:

1. Networking resources
2. Compute resources
3. Storage Resources. 

After learning the basics and configuring pre-requisite networking, we will then [deploy NetScaler ADC in AWS](https://www.youtube.com/watch?v=NvncDbmzgnY) to show how you can Load Balance a simple Website hosted on an EC2 instance via the NetScaler ADC. 


As a pre-requisite for this tutorial, please sign up and create your own AWS Free Tier account from the [sign in page](https://console.aws.amazon.com/console/home)

Follow along via links to AWS tutorial content in the Table of Contents below. 

# Table of Contents

## [Networking in AWS (VPC)](./VPC#VPC) ##
1. [Overview](/VPC#VPC-Overview)
2. [Creating a VPC](/VPC#VPC-Wizard)
3. [Creating Three Subnets](./VPC#VPC-Subnets)
    * [Management Subnet](./VPC#MGMT-Subnet)
    * [Server Subnet](./VPC#Server-Subnet)
    * [Client Subnet](./VPC#Client-Subnet)
4. [Creating Three Route Tables](./VPC#Route-Tables)
  * [Configure the MGMT Subnet Default Route Table](./VPC#MGMT-RT)
  * [Create and Configure the Server Subnet's Route Table](./VPC#Server-RT)
  * [Create and Configure the Client Subnet's Route Table](./VPC#Client-RT)
5. [Summary](./VPC#VPC-Summary)

**Summary of [Network Topolgy after completion](VPC/images/Base-NTW-Topology.jpg)**
  
## Storage in AWS ([S3](./S3#S3) and [EFS](./EFS#EFS)) ##

1. [S3](S3/)
  * [Overview](./S3#S3-Bucket)
  * [Create an S3 Bucket](./S3#S3-Bucket)
  * [Create a S3 Bucket](./S3#a-File-S3)
  * [Download a File from an S3 Bucket](./S3#Download-File-S3)
  * [Summary](./S3#S3-Summary) 
  
2. [EFS](EFS/)
  * [Overview](./EFS#EFS)
  * [Create an EFS Mount Point](./EFS#EFS-Wizard)
  * [Summary](./EFS#EFS-Summary)

## [Computing in AWS (EC2)](./EC2#EC2) ##
1. [Overview](./EC2#EC2-Overview)
2. [Launch an Windows EC2 Instance (Client Network)](./EC2/Windows-EC2/README.md#EC2-Windows)
  * [Overview EC2 Launch Wizard for Windows Server 2016 Instance](./EC2/Windows-EC2/README.md#EC2-Windows-Overview)
  * [RDP into Windows EC2 Instance](./EC2/Windows-EC2/README.md#Windows-RDP)
  * [Pull S3 Bucket files into the Windows Instance](./EC2/Windows-EC2/README.md#Windows-S3)
  * [Summary](./EC2/Windows-EC2/README.md#Windows-EC2-Summary)
3. [Launch a Linux EC2 Instance (Server Network)](./EC2/Ubuntu-EC2/README.md#Linux-EC2)
  * [Overview EC2 Launch Wizard for Ubuntu Server Instance](./EC2/Ubuntu-EC2/README.md#EC2-Ubuntu-Overview)
  * [SSH into Linux EC2 Instance, Update, and Install Pre-Reqs](./EC2/Ubuntu-EC2/README.md#SSH-Linux-EC2)
  * [Mount EFS volumes on the host](./EC2/Ubuntu-EC2/README.md#Linux-EFS-Mount)
  * [Host a WebApp on port 8080](./EC2/Ubuntu-EC2/README.md#Host-Webservers)
  * [Summary](./EC2/Ubuntu-EC2/README.md#EC2-Summary)
4. [Deploy NetScaler ADC in AWS](./EC2/Deploy-NS#Deploy-NS)
  * [Overview](./Deploy-NS#Deploy-NS-Overview)
  * [Provision a NetScaler ADC VPX 10 EC2 instance](./EC2/Deploy-NS#Deploy-NS-Provision)
  * [Configure NetScaler VPX via web console](./EC2/Deploy-NS#Deploy-NS-Config) 
  * [Configure public facing ENI](./EC2/Deploy-NS#Deploy-NS-Public-ENI). 
  * [Configure a simple Load balancer](./EC2/Deploy-NS#Deploy-NS-LoadBalancer)

**Summary of [Network Topology after completion](VPC/images/NS-NTW-Topology.png)**


 


  
  
