# Hosting-Wordpress-Website-on-AWS-
Hosting a wrodpress site on 3 Tire AWS Architecture

![Alt text](/Hosting-worpress-on-aws-infra.png)

# WordPress on AWS Project
## Overview

## This project focuses on establishing the foundational network infrastructure necessary for hosting a WordPress website on Amazon Web Services (AWS). It encompasses setting up a Virtual Private Cloud (VPC), configuring security groups, setting up EC2 instances, and installing WordPress, ensuring a robust and scalable environment. Below is a detailed breakdown of the project, the resources utilized, and the key learnings derived from this experience.
Prerequisites

## Before starting, ensure you have:

   -  An AWS account and Iam user
   -  Basic knowledge of AWS services
   -  Familiarity with WordPress and web hosting concepts
   -  A Github Account 
   -  AWS CLI configured on yor Machine

## Section 1: AWS Infrastructure Setup

## VPC Creation

    AWS Region Selection
        Chose an appropriate AWS region to minimize latency.
    VPC and DNS Setup
        Created a VPC and enabled DNS hostnames for internal network resolution.

## Internet Gateway and Subnets

    Internet Gateway
        Created and attached an Internet Gateway to the VPC to facilitate internet access.
    Subnets
        Created public and private subnets distributed across different availability zones for high availability.

## Route Tables and NAT Gateway

    Route Tables
        Configured public and private route tables to manage network traffic.
    NAT Gateway
        Set up a NAT Gateway to allow instances in private subnets to access the internet securely.

## Security Groups

    Security Group Configuration
        Configured security groups for various components including Application Load Balancer (ALB), Application Server, Database, EC2 Endpoint, and Elastic File System (EFS) to control inbound and outbound traffic.

## EC2 Instance Connect Endpoint

    Instance Connect Endpoint
        Created an EC2 instance connect endpoint for secure SSH access.
    EC2 Instance Setup
        Launched and connected to an EC2 instance within a private subnet.

## Section 2: Resource Setup and WordPress Installation
EFS Setup

    EFS File System
        Created an EFS file system for shared storage.
    Mount Targets
        Configured mount targets for each subnet to ensure accessibility.

## RDS Setup

    RDS Subnet Group
        Created a subnet group for the RDS instances.
    RDS Instance
        Launched an RDS instance to serve as the database backend for WordPress.

## EC2 Web Servers and Target Groups

    EC2 Instances
        Set up EC2 instances in private subnets to function as web servers.
    Target Groups
        Created target groups and associated them with the EC2 instances for load balancing.

## Application Load Balancer

    ALB Setup
        Created an Application Load Balancer and linked it with the target groups to distribute traffic evenly.

## WordPress  Script Installation using EC2 Lunch template User Data

    Requirements and Script
        Reviewed WordPress requirements and prepared an installation script.
    Execution
        Executed the script to install WordPress and configured it to use EFS for file storage.

## Section 3: Domain Setup, SSL, and Auto Scaling
Route53 and Domain Setup

    Domain Registration
        Registered a domain name and set up DNS records using Route53.

## SSL Certificate

    SSL Request
        Requested an SSL certificate for secure HTTPS access.
    HTTPS Configuration
        Configured HTTPS listener on the ALB and set up redirection from HTTP to HTTPS.
    WordPress SSL Settings
        Updated WordPress settings to use the SSL certificate.

## Auto Scaling Group

    Launch Template
        Created a launch template with the WordPress installation script.
    Auto Scaling Setup
        Configured an auto scaling group to ensure the application can scale based on demand.

## Final Steps

    Testing
        Tested the WordPress site to ensure functionality and performance.
  
    Scalability and High Availability
        Ensured the infrastructure supports scalability and high availability.

## Resources Used

    AWS Services: VPC, EC2, EFS, RDS, Route53, NAT Gateway, Application Load Balancer, Auto Scaling, Ec2 Endpoint
    Tools: AWS Management Console, AWS CLI
    Documentation: AWS official documentation, WordPress installation guides

## What i learnt

    Gained hands-on experience with AWS infrastructure setup and management.
    Learned to configure network components for a secure and scalable web application.
    Acquired skills in automating WordPress deployment on a cloud environment.
    Enhanced understanding of cloud best practices and high availability architectures.
