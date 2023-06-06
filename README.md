# Remote Attack Device (RAD) Platform

## About
The Remote Attack Device (RAD) Platform is an advanced penetration testing and red teaming solution utilizing a portable, mini PC. The RAD is connected to an on-site client network, establishes secure VPN connections to AWS EC2 instances (Kali Linux and Windows), and enables remote testing and wireless assessments. The device is designed to operate remotely, reducing the need for on-site presence of security professionals.

## Requirements
- [AWS Account](https://www.aws.amazon.com/free)
- Preconfigured Offensive [AWS EC2 instances](https://github.com/hackedbyagirl/Eris)
- Mini PC device with a wireless adapter (Ex: Raspberry Pi or Intel NUC)
- VPN solution for secure connection between the Mini PC and EC2 instances

## Getting Started
### 1. Setup AWS EC2 instances 
Create and configure two EC2 instances (Kali Linux and Windows) utilizing [Eris](https://github.com/hackedbyagirl/Eris) or the AWS Management Console.

*Note:* Make sure to allow SSH and RDP connections, respectively, in your AWS security groups and EC2 Instances.

### 2. Install necessary tools
Install required penetration testing tools on both Kali Linux and Windows instances. It is important to note that if you go the AWS Management Console route, this will have to be done manually, however, this step is addressed by the [Eris](https://github.com/hackedbyagirl/Eris) tool. 

### 3. Configure VPN 
Set up VPN connections on both instances to allow secure connections from the RAD platform. You can use AWS VPN Gateway or the built-in VPN capabilities of Kali and Windows.

### 4. Set up the RAD Platform 
Configure the Mini PC to establish VPN connections with the EC2 instances whenever it's connected to a network.

### 5. Manage your instances 
With the VPN connection active, you can remotely manage your EC2 instances via SSH (for Kali) and RDP (for Windows).

## Disclaimer
Please adhere to all applicable laws and obtain appropriate permissions before conducting any offensive security activities. Always follow best practices for security, such as regularly rotating passwords, limiting network exposure, and configuring firewalls and security groups properly.
