Project Title: AWS Load Balancer Setup with High Availability and Web
Application Load Balancing (Linux & Windows Servers)

Project Description: In this project, I configured a highly available
web application infrastructure using AWS Elastic Load Balancer (ALB) to
manage and distribute traffic across EC2 instances running both Linux
and Windows Server. The project involved setting up EC2 instances,
configuring web servers, setting up a Load Balancer with security and
health checks, and implementing CloudWatch monitoring for performance
tracking.

Project Steps & Documentation 1. Introduction This project demonstrates
the setup of a highly available web application with AWS Load Balancer,
distributed across Linux and Windows Server EC2 instances. The load
balancer ensures high availability, distributing traffic between both
servers based on health checks.

2\. Prerequisites To execute this project, the following are required:

Active AWS account

IAM permissions with access to EC2, Load Balancer, and CloudWatch

Basic knowledge of AWS, EC2 instances, Load Balancers, and web hosting

3\. Setting Up EC2 Instances 3.1. Create Linux Server Instance Launch
Instance:

Go to the EC2 Dashboard and select Launch Instance.

Choose Amazon Linux 2 AMI, select t2.micro instance type.

Configure instance details, add storage, and configure security groups
to allow HTTP, HTTPS, and SSH access.

Launch the instance.

Connect & Configure:

Use SSH to connect to the instance using the command: ssh -i
\"june5.pem\"
ec2-user@ec2-54-186-114-238.us-west-2.compute.amazonaws.com

Install and start the web server using: sudo yum install httpd -y sudo
service httpd start

The Linux web server is now running.

3.2. Create Windows Server Instance Launch Instance:

Go to the EC2 Dashboard and select Launch Instance.

Choose Windows Server 2019 Base AMI, and select the t2.micro instance
type.

Configure instance details, add storage, and configure security groups
to allow RDP, HTTP, and HTTPS access.

Launch the instance.

Connect & Configure:

Use RDP to connect to the Windows instance.

Install IIS via Server Manager by selecting Add roles and features -\>
Web Server (IIS).

The Windows Server is now set up to host a web application.

4\. Setting Up the Load Balancer 4.1. Create Application Load Balancer
(ALB) Navigate to the EC2 Dashboard, then select Load Balancers.

Click Create Load Balancer, and select Application Load Balancer (ALB).

Configure the ALB with the following settings:

Name: Provide a suitable name for the load balancer.

Scheme: Select internet-facing.

Listeners: Add listeners for HTTP (port 80) and/or HTTPS (port 443).

Availability Zones: Select the availability zones where your instances
are located.

4.2. Configure Security Groups Create a security group to allow
HTTP/HTTPS traffic to the load balancer.

4.3. Configure Target Group Create a new target group, choose instance
type, and configure health checks to monitor the health of EC2
instances.

4.4. Register Targets Register both Linux and Windows EC2 instances to
the target group to ensure traffic is directed to both servers.

4.5. Review and Create Review the configurations and click Create to
finalize the load balancer setup.

5\. Testing the Setup Access Load Balancer:

Retrieve the DNS name of the load balancer from the AWS Management
Console.

Navigate to the DNS name in a web browser.

Verify the load balancing between Linux and Windows servers by accessing
the application from the load balancer.

6\. Monitoring with CloudWatch CloudWatch Metrics:

Set up CloudWatch monitoring for both the load balancer and EC2
instances.

Track key metrics like request count, healthy/unhealthy hosts, and
latency.

Set Up Alarms:

Set up alarms to notify you if any critical thresholds (e.g., high CPU
utilization or instance failure) are crossed.

7\. Conclusion In this project, I successfully configured a highly
available web application on AWS using an Application Load Balancer
(ALB) with both Linux and Windows Server EC2 instances. The setup
ensures high availability and load balancing, and the integration with
CloudWatch provides real-time performance monitoring. This architecture
ensures the application can handle increased traffic while maintaining
performance and uptime.

Visuals (Screenshots) Linux Server Connected Successfully via SSH

Figure 1: Linux server connection via SSH.

Linux Web Hosting Configured

Figure 2: Linux web hosting running successfully.

Windows Server Installed and IIS Configured

Figure 3: IIS setup on Windows Server.

Load Balancer Created Successfully

Figure 4: Load balancer creation process.

Target Group Registered with Linux and Windows Servers

Figure 5: Target group registration.

CloudWatch Metrics

Figure 6: CloudWatch monitoring graph.

Testing Across Devices Mobile:

Successfully tested the setup on mobile devices for accessibility and
load balancing verification.
