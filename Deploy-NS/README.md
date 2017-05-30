# [NetScaler ADC in AWS](#Deploy-NS) #

[Citrix NetScaler on Amazon Web Services (AWS)](https://aws.amazon.com/marketplace/search/results?x=0&y=0&searchTerms=Citrix+Netscaler+ADC&page=1&ref_=nav_search_box) enables enterprises to rapidly and cost-effectively leverage world-class [NetScaler application delivery capabilities](https://www.citrix.com/products/netscaler-adc/) within their Amazon Web Services deployments. NetScaler on AWS combines the elasticity and flexibility of the AWS Cloud with the same optimization, security and control NetScaler provides for the most demanding websites and applications in the world. Because the corresponding Amazon Machine Image (AMI) is a packaging of the same binary used on NetScaler MPX™/NetScaler SDX™ hardware and NetScaler VPX™ virtual appliances, enterprises obtain all of the same L4-7 functionality familiar from their on-premise deployments, including load balancing, content switching, global server load balancing, application firewall and SSL VPN. This enables numerous compelling use cases, from hybrid cloud (i.e., spillover) and production delivery scenarios, to implementations for business continuity and application development and testing.

**Note:** There are many ways of deploying a NetScaler VPX in the cloud
  
  1. [Explicitly via the Market Place](https://aws.amazon.com/marketplace/search/results?x=0&y=0&searchTerms=netscaler&page=1&ref_=nav_search_box)
  2. [Cloud formation Template](https://console.aws.amazon.com/cloudformation/designer/home?templateURL=https%3A%2F%2Fs3.amazonaws.com%2Fawsmp-fulfillment-cf-templates-prod%2F63425ded-82f0-4b54-8cdd-6ec8b94bd4f8.01d3948e-aa71-48a7-8253-24fe14fc049b.template&region=us-east-1)
  3. [Single click Deploy](TBD)

In this section, we will show you can Deploy a NetScaler ADC in AWS within your VPC to front end a simple web application through provisioning a NetScaler VPX EC2 instance from the AWS market place (1. from above). Later we will explore CloudFormation deployments. 

##  [Overview](#Deploy-NS-Overview) ##
Before we begin, I want to outline our objectives in this module. In this module we will :
  
  1. Provision a NetScaler ADC VPX 10 EC2 instance
    * It's default interface will reside on the management network interface with a static IP of `172.16.10.100`.
    * This instance will have an additional NIC on the server subnet with a static IP of `172.16.20.100`. 
  2. Logon to the NetScaler VPX management web console
    * Assign a [SNIP](https://docs.citrix.com/en-us/netscaler/11/networking/ip-addressing/configuring-netscaler-owned-ip-addresses/configuring-subnet-ip-addresses-snips.html) and update the routing table to use the *Server Subnet*'s gateway that will forward all internet access to the internet via the [NAT Gateway](../VPC#Server-RT).
    * Configure a nameserver for DNS resolution. 
  3. Configure public facing [ENI](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-eni.html). 
    * Assign a private IP to the ENI of `172.16.30.100` and associate it with an [Elastic IP](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for direct access via a public IP. 
  4. Configure a simple Load balancer. 
    * This Load Balancer will have an IP of `172.16.30.100` and load balance the web service hosted on the linux EC2 isntance from the [EC2 module](../EC2/Ubuntu-EC2#Host-Webservers)

## [Provision a NetScaler ADC VPX 10](#Deploy-NS-Provision) ##

Begin by 

## [Configure NetScaler VPX  via web console](#Deploy-NS-Provision) ##


## [Configure NetScaler VPX via web console](#Deploy-NS-Config) ##


## [Configure public facing ENI](./Deploy-NS#Deploy-NS-Public-ENI) ##


## [Configure a simple Load balancer](./Deploy-NS#Deploy-NS-LoadBalancer) ##

## [Summary](#EC2-Summary) ##

	
 


