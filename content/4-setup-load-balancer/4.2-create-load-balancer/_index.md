---
title: "Create Load Balancer"
date: "`r Sys.Date()`"
weight: 2
chapter: false
pre: "<strong>4.2. </strong>"
---

#### Create Load Balancer

In the EC2 management interface, on the left-hand panel:

- Select **Load Balancers**
- Click on the **Create Load Balancer** button

![4.2.1](/images/4-setup-load-balancer/4.2.1.png)

The **Compare and select load balancer type** dialog will appear.

- In the Load balancer types section:
  - Under **Application Load Balancer**
  - Click **Create**

![4.2.2](/images/4-setup-load-balancer/4.2.2.png)

You will see the **Create Application Load Balancer** dialog.

- In the **Basic configuration** section:
  - Load balancer name: `FCJ-Management-LB`
  - Scheme: **Internet-facing**
  - Load balancer IP address type: **IPv4**

![4.2.3](/images/4-setup-load-balancer/4.2.3.png)

- In the **Network mapping** section:
  - Select VPC: **AutoScaling-Lab**
  - Choose Public Subnets: **ap-southeast-1a**, **ap-southeast-1b**, **ap-southeast-1c**. Note to select **public subnet**.

![4.2.4](/images/4-setup-load-balancer/4.2.4.png)

- In the **Security groups** section:
  - Security group: **FCJ-Management-SG**
- In the **Listeners and routing** section:
