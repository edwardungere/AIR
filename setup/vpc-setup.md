# VPC Setup

## Create VPC

Name: **my-vpc** 

IPv4 CIDR Block: **10.0.0.0/16** 

Optional: **Enable DNS hostnames**

## Create Public Subnets

## Create Private Subnets

Select: **my-vpc**

Name: **private-1a**

Availability Zone: **us-east-1a**

IPv4 CIDR Block: **10.0.1.0/24**

Name: **private-1b**

Availability Zone: **us-east-1b**

IPv4 CIDR Block: **10.0.2.0/24**

## Create Private Route Table

Name: **private-rt**

VPC: **my-vpc**

Subnet associations: **private-1a**, **private-1b**

## Edit Main Route Table





