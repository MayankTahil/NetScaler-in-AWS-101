# Introduction to AWS and NetScaler
In this tutorial, we will explore the basics of AWS when provisioning Network resources, Compute resources, and Storage Resources. After learning the basics and configuring pre-requisite networking, we will then deploy NetScaler ADC in AWS to show how you can Load Balance a simple Website hosted on an EC2 instance via the NetScaler ADC. 


As a pre-requisite for this tutorial, please sign up and create your own AWS Free Tier account from the [sign in page](https://console.aws.amazon.com/console/home)


## Networking in AWS (VPC)
In this Section we will explore how to configure cloud networking in AWS. If you have not already done so, logon to [htps://consle.aw.amazon.com](consol.aws.asazon.com) to gain access to the AWS dashboard. Once you have logged on, in the top left you will notice a "Service" drop down which lists all of your services availible that you can subscribe to and consume for your cloud infrastructure. For configuring our cloud's networking resources, we will primarily be working in the VPC dashboard. Click on VPC under services to enter the VPC dashboard. 

![AWS Dashboard Services](images/AWS-VPC-Dashboard.gif)

Once you're in the VPC dashboard, you will notice in the top right my selected region is *N. California*. This designates where my resources in the cloud will be geographically residing. Each Region consists of multiple Availiblity Zones for high availiblity to mitigate your failure domain. You can view how many and which availibility zones are availible for given regions on AWS' website. In this tutorial, we will be concerning ourselves with 1 region and 1 availiblity zone to deploy all our networking resources as you'll soon see.

![AWS Regions and Availibility Zones](images/AWS-AZ.gif)

### Creating a VPC
Before we begin, I want to outline our objectives in this tutorial. In this tutorial we aim to create our very own [Virtual Pivate Cloud](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html) which lets us provision logically isolated sections of the the cloud where we can later launch AWS resources like virtual machines, also known as EC2 instances, in virtual networks that we will create within the VPC. 

We will create three of these virtual networks also known as [subnets](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Subnets.html). 

1. One subnet will be created for **management** as a private subnet with no access to the internet what so ever.
2. One subnet will be created for back-end **servers** as a private subnet with only outbount access to the internet for software updates for example. 
  * **Note**: virutal machines or EC2 instances deployed in this private subnet of VPC cannot be accessed from the Internet directly because you cannot assign them a public IP. We'll see why shortly.
  
3. One subnet will be created for **client** facing traffic as a public subnet which has outbound and static IP mapping capability for direct inbound access from the internet. 

Lets begin by creating our first VPC. Click on *"Your VPCs"* on the left column and notice that a default VPC has already been created for us. This is out of the box configuration from AWS to quickly deploy compute resources. However, we will ignore the defaults and be explicit in creating our own networks.

Begin by clicking *"Create VPC"* button on top and then follow the wizard. 

In the creation wizard, you will only need to specify

1.  Name: `Demo-VPC`
2.  CIDR block : `172.16.0.0/16`
	  * This CIDR block will encompass all your availible IP's within the VPC to segment out into specific subnets and networks.
3. Click *Yes Create* and continue. 

![Create a new VPC](images/new-VPC.gif)

### Creating Three Subnets

Now we will create the three subnets outlined above. Click on *Subnets* on the left pane and then click the *Create Subnet* button for each new subnet to be created. Here we will give the following subnets the following parameters: 

***Management Subnet:***

  * **Name** `MGMT` for management traffic
  * **VPC** `Demo-VPC`
  * **IPv4 CIDR Block** range of `172.16.10.0/24`
  * **Availibility Zone** `us-west-1a`
  * **Note:** In subsequent steps, we will ensure that this subnet will not have any access to and from the internet.

![Create MGMT Subnet](images/MGMT-subnet.gif)

***Server Subnet:***

  * **Name** `Server` for private back-end server traffic
  * **VPC** `Demo-VPC`
  * **IPv4 CIDR Block** range of `172.16.20.0/24`
  * **Availibility Zone** `us-west-1a`
  * **Note:** In subsequent steps, we will ensure that this subnet will only have outbound access to the internet and that no direct connections from the internet can be established. We will configure a [NAT Gateway](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/vpc-nat-gateway.html) for this use case.

![Create Server Subnet](images/Server-subnet.gif)

***Client Subnet:***

  * **Name** `Client` for Direct web-facing internet traffic. 
  * **VPC** `Demo-VPC`
  * **IPv4 CIDR Block** range of `172.16.30.0/24` 
  * **Availibility Zone** `us-west-1a`
  * **Note:** In subsequent steps, we will configure the ability for resources deployed in this network to have direct access to and from the internet with Public IPs. We will configure an [Internet Gateway](http://docs.aws.amazon.com/AmazonVPC/latest/UserGuide/VPC_Internet_Gateway.html) for this use case.

![Create Client Subnet](images/Client-subnet.gif)
