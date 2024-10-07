# AWS Hands-on

### Phase - 1: Creating a VPC & Subnet (Public/Private)
#### Task - 1: 
- **Step 1**: Create VPC 
  - *VPC settings* >
    - Resources to create -> `VPC and more`
    - Name tag auto-generation -> `handson-user1-vpc`
    - IPv4 CIDR block -> `10.0.0.0/16`
    - IPv6 CIDR block -> `No IPv6 CIDR block`
    - Tenancy -> `Default`
    - Number of Availability Zones (AZs) -> `2` 
    - *Customize AZs* >
      - First availability zone -> `us-west-2a`
      - Second availability zone -> `us-west-2b`
    - Number of public subnets -> `2`
    - Number of private subnets -> `2`
    - *Customize subnets CIDR blocks* > 
      - Public subnet CIDR block in us-west-2a -> `10.0.0.0/24`
      - Public subnet CIDR block in us-west-2b -> `10.0.1.0/24`
      - Private subnet CIDR block in us-west-2a -> `10.0.2.0/24`
      - Private subnet CIDR block in us-west-2b -> `10.0.3.0/24`
    - NAT gateways ($) -> `None`
    - VPC endpoints -> `None`
    - *DNS options* >
      - [x] Enable DNS hostnames
      - [x] Enable DNS resolution
- **Step 2**: Click on `Create VPC`

### Phase - 2: Create EC2 Instance & Install Wordpress
#### Task - 1: 
- **Step 1**: Create EC2 Instance
  - *Name and tags* > 
    - Name -> `rk-webserver-user1`
  - *Application and OS Images (Amazon Machine Image)* >
    - Amazon Machine Image (AMI) -> `Amazon Linux 2023 AMI (HVM) - Kernel 5.10, SSD Volume Type - Free tier eligible`
    - Architecture -> `64-bit (x84)`
  - *Instance type* >
    - Instance type -> `t2.micro`
      - [ ] All generations
  - *Key pair (login)* > 
    - Key pair name *- required* -> `Proceed without a key pair (Not recommended) - Default value`
  - *Network settings* >  Click on `Edit` button
    - VPC *- required* -> `handson-user1-vpc`
    - Subnet -> `handson-user1-subnet-public1-us-west-2a`
    - Auto-assign public IP -> `Enable`
    - Firewall (security groups) -> `Create security group`
    - Security group name *- required* -> `rk-web-user1`
    - Description *- required* -> Example: `rk-web-user1 created 2024-10-04T07:13:19.225Z`
    - *Inbound Security Group Rules* >
      - Click on `Add security groups rule`
      - *Security group rule 2* >
        - Type -> `HTTP`
        - Source type -> `Custom`
        - Source -> `0.0.0.0/0`
  - *Advanced details* > 
    - User data *- optional* ->
```bash
!/bin/bash

yum -y update
yum -y install php httpd mysql

PHP_VERSION=`php -v | head -n 1 | awk '{print $2}' | awk -F "." '{print $1}'`#
while [  ${PHP_VERSION} -ne 7 ]
do
amazon-linux-extras install php7.4 -y
PHP_VERSION=`php -v | head -n 1 | awk '{print $2}' | awk -F "." '{print $1}'`
done

yum -y install php-mbstring php-xml

wget http://ja.wordpress.org/latest-ja.tar.gz -P /tmp/
tar zxvf /tmp/latest-ja.tar.gz -C /tmp
cp -r /tmp/wordpress/* /var/www/html/
chown apache:apache -R /var/www/html

systemctl enable httpd.service
systemctl start httpd.service
```

- **Step 2**: Click on `Launch Instance`

### Phase - 3: Create RDS MySQL DB Instance
#### Task - 1:
- **Step 1**: Create Security Group
  - *Basic details* > 
    - Security group name -> `rk-db-user1`
    - Description -> `RDS for MySQL`
    - VPC -> `handson-user1-vpc`
  - *Inbound rules* > Click on `Add rule`
    - Type -> `MYSQL/Aurora`
    - Source -> `Custom`
      - *Search* the the following: `rk-web-user1`
- **Step 2**: Click on `Create security group`

#### Task - 2:
- **Step 1**: Create DB subnet group
  - *Subnet group details* > 
    - Name -> `rk-db-subnet-user1`
    - Description -> `RDS for MySQL`
    - VPC -> `handson-user1-vpc`
  - *Add subnets* >
    - Availability Zones -> `us-west-2a` and `us-west-2b`
    - *Subnets (Private Only)* >
      - us-west-2a -> `10.0.2.0/24`
      - us-west-2b -> `10.0.3.0/24`
- **Step 2**: Click on `Create`

#### Task - 3:
- **Step 1**: Create database
  - *Choose a database creation method* > 
    - Select the following: `Standard create`
  - *Engine options* >
    - Engine type -> `MySQL`
  - *Templates* >
    - Select the following: `Free tier`
  - *Settings* > 
    - DB instance identifier -> `rk-rds-user1`
    - Master username -> `admin`
    - Credentials management -> `Self managed`
    - Master password -> `Plan-b1234`
    - Confirm master password `Plan-b1234`
  - *Connectivity* >
    - Compute resource -> `Don’t connect to an EC2 compute resource`
    - Virtual private cloud (VPC) ->  `handson-user1-vpc`
    - DB subnet group -> `rk-db-subnet-user1`
    - Public access -> `No`
    - VPC security group (firewall) -> `Choose existing`
    - Existing VPC security groups -> `rk-db-user1`
    - Availability Zone -> `us-west-2a`
  - *Additional configuration* >
    - *Database options* > 
      - Initial database name -> `wordpress`
      - *Backup* > Uncheck the following:
        - [ ] Enable automated backups
- **Step 2**: Click on `Database create`

### Phase - 4: Create an ELB
#### Task - 1:
- **Step 1**: Create Security Group
  - *Basic details* > 
    - Security group name -> `rk-elb-user1`
    - Description -> `ELB for User`
    - VPC -> `handson-user1-vpc`
  - *Inbound rules* >
    - Type -> `HTTP`
    - Source -> `Anywhere-IPv4`
      - `0.0.0.0/0`
- **Step 2**: Click on `Create security group`
 
#### Task - 2:
- **Step 1**: Create target group
  - *Basic configuration* >
    - Choose a target type -> `Instance`
    - Target group name -> `rk-target-user1`
    - VPC -> `handson-user1-vpc`
  - *Health checks* > 
    - Health check path -> `/wp-includes/images/blank.gif`
- **Step 2**: Click on `Next`
  - *Available instances* > Select available Instance.
    - [x] | i-04fe338cbea4b0f85 | rk-instance-1 | Running | web-user1 |
  - Click on `Include as pending below`
- **Step 3**: Click on `Create Target Group`

#### Task - 3:
- **Step 1**: Create load balancer
  - *Basic configuration* >
    - Load balancer name -> `rk-elb-user1`
  - *Network mapping* > 
    - VPC -> `handson-user1-vpc`
    - *Mappings* > 
      - *Availability Zones* > Checked the both
        - [x] *us-west-2a (usw2-az2)* >
          - Subnet -> `handson-user1-subnet-public1-us-west-2a`
        - [x] *us-west-2b (usw2-az1)*
          - Subnet -> `handson-user1-subnet-public2-us-west-2b`
  - *Security groups* >
    - Security groups -> `rk-elb-user1`
  - *Listeners and routing* >
    - *Listener  HTTP:80*
      - Protocol -> `HTTP`
      - Port -> `80`
      - *Default action*
        - Forward to -> `rk-target-user1`

- **Step 2**: Click on `Create load balancer`
- **Step 3**: Copy the DNS and Save somewhere.
  - *Example:* >
    - DNS -> `rk-elb-user1-1259643476.us-west-2.elb.amazonaws.com`

### Phase - 5: Initialize Wordpress & Create a simple blog
#### Task - 1:
- **Step 1:** Open the DNS in browser.
  - DNS -> `rk-elb-user1-1259643476.us-west-2.elb.amazonaws.com`
  
- **Step 2**: Click on `Let’s get started!` button.

- **Step 3**: Initialize the Wordpress.
  - Database name -> `wordpress`
  - Username -> `admin`
  - Password -> `Plan-b1234`
  - Database hostname -> `rk-rds-user1.cqvkhlhgbd99.us-west-2.rds.amazonaws.com`
    - For Database hostname, Open RDS > Open Database >
      - Click on created database `rk-rds-user1` .
      - Copy Endpoint `rk-rds-user1.cqvkhlhgbd99.us-west-2.rds.amazonaws.com` 
      - Paste in the Database hostname of Wordpress.
- **Step 4**: Click on `send` button.
