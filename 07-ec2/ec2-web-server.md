# Amazon EC2 Web Server

## Overview

An Amazon EC2 instance was deployed within the public subnet of the AS2C AWS cloud infrastructure.

The EC2 instance hosts an Apache HTTP web server and provides a publicly accessible web application.

## EC2 Configuration

- Instance Name: AS2C-Web-Server
- Operating System: Amazon Linux 2023
- Instance Type: t3.micro
- VPC: AS2C-Network
- VPC CIDR: 10.0.0.0/16
- Subnet: AS2C-Public-Subnet
- Subnet CIDR: 10.0.1.0/24
- Web Server: Apache HTTP Server

## Web Server Configuration

Apache was installed using the Amazon Linux package manager.

The service was started and configured to automatically start after system reboot.

```bash
sudo dnf update -y
sudo dnf install -y httpd
sudo systemctl start httpd
sudo systemctl enable httpd
sudo systemctl status httpd
