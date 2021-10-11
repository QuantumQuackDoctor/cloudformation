# Cloudformation Repository

This repository contains the base infrastructure template

## Base Infrastrucure template

This template contains

- Jenkins pipeline
- Jenkins ec2.ami
- Target Groups
- VPC Subnets
- Securtity Groups
- Load Balancers
- ECS Clusters
- Route Tables
- Gateways (nat and internet)
- IAM Roles and Policies
- Secrets
- ECR Repositories
- S3 Buckets
- Route53 domain and subdomain,
- resolver endpoints,
- hosted zone
- Certificates\*
- RDS

AWS secrets manager is used for sensitive data and nonsensitive data is specified in outputs

### Secrets Manager

- DBUsername
- DBPassword
- DBEndpoint
- DBName
- DBPort
- ServiceSecurityGroup
- FargateRoleARN
- VPCID
- PublicSubnet1
- PublicSubnet2
- PrivateSubnet1
- PrivateSubnet2
- S3AccessIdentity
- LBListenerARN
- UserTGArn
- OrderTGArn
- RestaurantTGArn
- ECSClusterName
- HostedZoneId
- AdminPortalDomainName
- UserPortalDomainName
- DriverPortalDomainName
