# Introduction to AWS and NetScaler
In this tutorial, we will explore the basics of AWS when provisioning:

1. Networking resources
2. Compute resources
3. Storage Resources. 

After learning the basics and configuring pre-requisite networking, we will then [deploy NetScaler ADC in AWS](https://www.youtube.com/watch?v=NvncDbmzgnY) to show how you can Load Balance a simple Website hosted on an EC2 instance via the NetScaler ADC. 


As a pre-requisite for this tutorial, please sign up and create your own AWS Free Tier account from the [sign in page](https://console.aws.amazon.com/console/home)

Follow along via links to AWS tutorial content in the Table of Contents below. 

# Table of Contents

### [Networking in AWS (VPC)](./VPC#VPC)
1. Creating a VPC
2. Creating Three Subnets
  * Management Subnet
  * Server Subnet
  * Client Subnet
3. Creating Three Route Tables
  * Configure the MGMT Subnet Default Route Table
  * Create and Configure the Server Subnet's Route Table
  * Create and Configure the Client Subnet's Route Table

  **Summary of [Network Topolgy after completion](VPC/images/Base-NTW-Topology.jpg)**

### [Computing in AWS (EC2)](./EC2#EC2)
1. Launch an Windows EC2 Instance (Client Network)
  * Launch EC2 Instance Wizard
  * Allocate an Elastic IP (EIP)
  * RDP into Windows EC2 Instance
2. Launch a Linux EC2 Instance (Server Network)
  * Launch EC2 Instance Wizard
  * SSH into Linux EC2 Instance
  * Host Two Webservers on port 80, 81, 82
  * Configure Custom Security Groups Rules

  **Summary of [Network Topology after completion](EC2/images/EC2-NTW-Topology.jpg)**

### Storage in AWS ([S3](./S3#S3), [EFS](./EFS#EFS), and [EBS](./EBS#EBS))
1. [S3](S3/)
  * Create an S3 Bucket
  * Put a File in the Bucket
  * Retreive the File from the Bucket
2. [EFS](EFS/)
  * Create an EFS Mount Point
  * Store data in the EFS Mount
  * Launch a Linux EC2 instance within EFS
  * Retreive Files from the EFS
3. [EBS](EBS/)
  * PLACE HOLDER

### [Deploy NetScaler ADC in AWS](./Deploy-NS#Deploy-NS)
1. EC2 Launch Wizard for NetScaler VPX 1000 (MGMT Subnet)
2. Attach Additional ENI's
  * ENI on Server Subnet
      * Allocate 1 private IP
  * ENI on Client Subnet
      * Allocate 2 private IPs
3. Configure NetScaler IP's
  *  Server Subnet SNIP
  *  Client Subnet SNIP
  *  Client Subnet VIP
4. Allot EIP for VIP for External Access.
5. Validate Configuration
  
  **Summary of [Network Topology after completion](Deploy-NS/images/NS-ADC-NTW-Topology.jpg)**


 


  
  