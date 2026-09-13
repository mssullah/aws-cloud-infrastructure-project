# AWS Cloud Architecture

## Overview

The AS2C cloud infrastructure is designed using Amazon Web Services (AWS) with a dedicated Virtual Private Cloud (VPC).

                         INTERNET
                             │
                             ▼
                    ┌─────────────────┐
                    │ Internet Gateway│
                    └────────┬────────┘
                             │
                ┌────────────▼────────────┐
                │       AS2C-Network      │
                │       10.0.0.0/16       │
                │                         │
                │ ┌─────────────────────┐ │
                │ │   PUBLIC SUBNET     │ │
                │ │   10.0.1.0/24       │ │
                │ │                     │ │
                │ │  EC2 Web Server     │ │
                │ │ AS2C-Web-Server     │ │
                │ └──────────┬──────────┘ │
                │            │            │
                │ ┌──────────▼──────────┐ │
                │ │   PRIVATE SUBNET    │ │
                │ │   10.0.2.0/24       │ │
                │ │                     │ │
                │ │      Database       │ │
                │ └─────────────────────┘ │
                └─────────────────────────┘

The architecture separates public-facing web resources from private database resources to improve network organization and security.

## VPC

- Name: AS2C-Network
- CIDR: 10.0.0.0/16

## Public Subnet

- Name: AS2C-Public-Subnet
- CIDR: 10.0.1.0/24
- Purpose: Web server deployment

## Private Subnet

- Name: AS2C-Private-Subnet
- CIDR: 10.0.2.0/24
- Purpose: Database resources

## Main AWS Components

- Amazon VPC
- Public Subnet
- Private Subnet
- Internet Gateway
- Route Tables
- Amazon EC2
- Security Groups

## Architecture Principle

The web server is placed in the public subnet to support controlled internet access, while database resources are planned for the private subnet to reduce direct exposure to the public internet.
