# AWS Overview

## Starting EC2 instance

1. Make sure you are in **N. Virginia (us-east-1)**
2. Click on Launch EC2 in Instances section of AWS EC2
    1. Name: (your 6+2)
    2. Pick **Amazon Linux 2 AMI**  (!!)
    3. Leave instance type **t2.micro **
    4. Create new key pair (label it with your 6+2)
    5. Network settings -> Firewall -> (*) Select existing security group
     and choose **class_security_group** (if you don't see it verify that you are in N. Virginia (upper right hand corner)
    6. Advanced details -> User data (bottom of the screen – leave the rest default):

```
#!/bin/bash
yum update -y
amazon-linux-extras install -y R4
yum install -y  https://download2.rstudio.org/server/centos7/x86_64/rstudio-server-rhel-2023.03.0-386-x86_64.rpm
echo "mypwd" | passwd ec2-user --stdin
```
