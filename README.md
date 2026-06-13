# Build a Virtual Private Cloud using LocalStack

## Overview

This project demonstrates the fundamentals of AWS networking by creating a Virtual Private Cloud (VPC) using LocalStack. The project covers VPC creation, subnet configuration, internet gateway setup, and network connectivity concepts.

## Technologies Used

* AWS CLI
* LocalStack
* Amazon VPC
* Docker

## Architecture

```text
Internet
   │
Internet Gateway
   │
VPC (10.0.0.0/16)
   │
Public Subnet (10.0.0.0/24)
```

## Project Objectives

* Create a custom VPC
* Configure a CIDR block
* Create a subnet inside the VPC
* Create an Internet Gateway
* Attach the Internet Gateway to the VPC
* Understand AWS networking fundamentals

## Resources Created

### VPC

| Property   | Value                 |
| ---------- | --------------------- |
| VPC ID     | vpc-4063c5316f17197ea |
| CIDR Block | 10.0.0.0/16           |
| State      | Available             |

### Subnet

| Property   | Value         |
| ---------- | ------------- |
| CIDR Block | 10.0.0.0/24   |
| Type       | Public Subnet |

### Internet Gateway

| Property            | Value                 |
| ------------------- | --------------------- |
| Internet Gateway ID | igw-4e34a9c9fa88867ee |
| State               | Attached              |

## Commands Executed

### Create VPC

```bash
aws --endpoint-url=http://localhost:4566 ec2 create-vpc \
--cidr-block 10.0.0.0/16
```

### Create Subnet

```bash
aws --endpoint-url=http://localhost:4566 ec2 create-subnet \
--vpc-id vpc-4063c5316f17197ea \
--cidr-block 10.0.0.0/24
```

### Create Internet Gateway

```bash
aws --endpoint-url=http://localhost:4566 ec2 create-internet-gateway
```

### Attach Internet Gateway

```bash
aws --endpoint-url=http://localhost:4566 ec2 attach-internet-gateway \
--internet-gateway-id igw-4e34a9c9fa88867ee \
--vpc-id vpc-4063c5316f17197ea
```

## Concepts Learned

### Virtual Private Cloud (VPC)

A VPC is a logically isolated virtual network where AWS resources can be launched and managed securely.

### CIDR Blocks

CIDR notation defines the IP address range available within a network.

* 10.0.0.0/16 → 65,536 IP addresses
* 10.0.0.0/24 → 256 IP addresses

### Subnets

Subnets divide a VPC into smaller network segments and help organize resources based on access requirements.

### Internet Gateway

An Internet Gateway allows communication between resources inside a VPC and the public internet.

## Verification

The following resources were successfully verified:

* VPC creation
* Subnet creation
* Internet Gateway creation
* Internet Gateway attachment

## Screenshots

Add screenshots in the `screenshots/` folder:

* vpc-created.png
* subnet-created.png
* internet-gateway-created.png
* internet-gateway-attached.png

## Author

Sakthi Balamurugan

Cloud Computing Student | AWS & Cloud Engineering Learner
