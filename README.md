# Introduction to AWS and NetScaler
In this tutorial, we will explore the basics of AWS for provisioning Network resources, Compute resources and Storage Resources. After learning the basics and configuring pre-requisite networking, we will then deploy NetScaler ADC in AWS to show how you can Load Balance a simple Website in AWS via the NetScaler ADC. 

## Networking in AWS (VPC)
In this Section we will explore how to configure cloud networking in AWS. If you have not already done so, logon to consol.aws.amazon.com to gain access to the AWS dashboard. Once you logon, in the top right you will notice a "Service" drop down which lists all of your services availible that you can subscribe to and consume for your cloud infrastructure. For configuring our cloud's networking resources, we will primarily be working in the VPC dashboard. Click on VPC under services to enter the VPC dashboard. 

![AWS Dashboard Services](/images/AWS-VPC-Dashboard.gif)

Once you're in the VPC dashboard, you will notice in the top right my selected region is N. California. This designates where my resources in the cloud will be physcially residing. Each Region consists of multiple Availiblity Zones for high availiblity to mitigate your failure domain. You can view how many and which availibility zones are availible for given regions on AWS' website. In this tutorial, we will be concerning ourselves with 1 region and 1 availiblity zone to deploy all our networking resources as you'll soon see.

### Creating a VPC
Before we begin, I want to outline our objectives in this tutorial. In this tutorial we aim to create our very own Virtual Pivate Cloud which lets us provision logically isolated sections of the Amazon Web Services (AWS) cloud where we can later launch AWS resources like virtual machoens also known as EC2 instances in a virtual network that we will create within the VPC. We will create three of these virtual networks also known as subnets. 
	1: One subnet will be created for management as a private subnet with no access to the internet what so ever.
	2: One subnet will be created for back end servers as a private subnet with only outbount access to the internet for software updates for example. Note: virutal machines or EC2 instances deployed in this private subnet of VPC cannot be accessed from the Internet directly because you cannot assign them a public IP. We'll see why shortly. 
	3: One subnet will be created for client facing traffic as a public subnet which has outbound and static IP mapping capability for direct inbound access from the internet. 

Lets begin by creating our first VPC. Click on "Your VPCs" on the left column and notie that a default VPC has already created for us. This is out of the box configuration from AWS to quickly deploy compute resources. However, we will ignore the defaults and be explicit in creating our own networks. Begin by clicking "Create VPC" button on top. 

In the creation wizard, you will only need to specify
	1: a name: Demo-VPC
	2: a CIDR block : 172.16.0.0/16 which will encompass all your availible IP's availible within the VPC to segment out into specific subnets and networks. 

Click Yes Creatae and continue. 




