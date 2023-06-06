# Remote Attack Device (RAD) Platform

## About
The Remote Attack Device (RAD) Platform is an advanced penetration testing and red teaming solution utilizing a portable, mini PC. The RAD is connected to an on-site client network, establishes secure VPN connections to AWS EC2 instances (Kali Linux and Windows), and enables remote testing and wireless assessments. The device is designed to operate remotely, reducing the need for on-site presence of security professionals.

## Requirements
- [AWS Account](https://www.aws.amazon.com/free)
- Preconfigured Offensive [AWS EC2 instances](https://github.com/hackedbyagirl/Eris)
- Mini PC device with a wireless adapter (Ex: Raspberry Pi or Intel NUC)
- VPN solution for secure connection between the Mini PC and EC2 instances

## Getting Started
1. Generate Offensive AWS AMI Base Images
2. Setup and Deploy AWS EC2 instances 
### 1. Generate Offensive AWS AMI Base Images
Utilizing [Eris](https://github.com/hackedbyagirl/Eris), a specialized tool designed for creating Offensive Amazon Machine Images (AMIs), create two base images: one for Kali Linux and another for Windows. These AMIs will come pre-equipped with the necessary penetration testing and red teaming tools for both systems. Once the AMIs are ready, they can be seamlessly deployed as AWS EC2 instances. 

If you would like to add additional features, you can manually adjust the EC2 Instance after it has been deployed or edit the configuration of each box using `Eris`. These additional features may include:
- Additional offensive tools
- VPN connections on both instances to allow secure connections from the RAD platform (You can use AWS VPN Gateway or the built-in VPN capabilities of Kali and Windows.)

> *Note*: The builder does *not* manage AMIs. Once it creates an AMI and stores it in your account, it is up to you to use, delete, etc. the AMI. (Ex: Terraform)

### 2. Setup and Deploy AWS EC2 instances 
Utilizing [Eris-deploy](https://github.com/hackedbyagirl/Eris-deploy), a specialized tool designed for deploying the Amazon Machine Images (AMIs) created above, to EC2 Instances. This tool will allow you to setup permissions such as SSH and RDP connections, respectively, in your AWS security groups and EC2 Instances and ensure a secure connection to your Mini PC device.

### 4. Configure the RAD Device 
You'll want to configure the Mini PC as a VPN client, to establish VPN connections with each VPN server on the EC2 instances once conntected to a network. This will create a secure tunnel between the NUC and the EC2 instances, allowing for remote testing. You may also want to configure the mini pc to automatically establish this VPN connection whenever it's plugged into a network.

### 5. Manage your instances 
With the VPN connection active, you can remotely manage your EC2 instances via SSH (for Kali) and RDP (for Windows).

## Disclaimer
Please adhere to all applicable laws and obtain appropriate permissions before conducting any offensive security activities. Always follow best practices for security, such as regularly rotating passwords, limiting network exposure, and configuring firewalls and security groups properly.
