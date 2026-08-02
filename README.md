# Deploying-a-Linux-Web-Server-on-Microsoft-Azure
Linux web server deployment on Microsoft Azure using a Virtual Machine and Apache. Provisioned an Azure Linux VM, installed Apache, and deployed a custom HTML webpage via public IP.

Project 2: Deploying a Linux Web Server on Microsoft Azure
Author: Maurrin Carter
Date: August 2, 2026
Platform: Microsoft Azure
Difficulty: Beginner-Intermediate

Project Overview
This project demonstrates how to provision a Linux Virtual Machine on Microsoft Azure, install and configure the Apache web server, and deploy a custom HTML webpage accessible via a public IP address. This project builds core cloud engineering skills including VM provisioning, SSH remote access, Linux package management, and web server configuration.

Technologies Used
Microsoft Azure (Virtual Machine, Networking, NSG)
Ubuntu Linux (22.04 LTS)
Apache2 Web Server
SSH (Secure Shell)
HTML
Nano / Terminal (CLI)
Skills Demonstrated
Cloud infrastructure provisioning on Azure
Linux command line navigation
Remote server access via SSH
Web server installation and management
Custom web page deployment
Network Security Group (NSG) configuration
Step-by-Step Process
Step 1: Create the Virtual Machine
Provisioned a new Linux Virtual Machine in the Azure Portal with the following configuration:

VM Name: project2-vm
Region: East US
Image: Ubuntu Server 22.04 LTS
Size: Standard B1s
Authentication: SSH public key
Username: azure-cp1
📸 Screenshot: Azure Portal VM overview showing public IP and Running status

Step 2: Configure Network Security Group (NSG)
Added inbound security rules to allow web and remote access traffic:

Port 22 - SSH (remote terminal access)
Port 80 - HTTP (web traffic)
📸 Screenshot: NSG inbound rules showing ports 22 and 80 open

Step 3: Connect via SSH
Connected to the virtual machine remotely from a local terminal using the SSH command:

ssh -i ~/.ssh/id_rsa azure-cp1@20.84.74.103
Successful connection confirmed by the terminal prompt:
azure-cp1@project2-vm:~$

📸 Screenshot: Terminal showing successful SSH connection

Step 4: Install Apache Web Server
Updated the package manager and installed the Apache2 web server:

sudo apt update
sudo apt install apache2 -y
📸 Screenshot: Terminal showing Apache2 installation completing successfully

Step 5: Verify Apache is Running
Confirmed Apache started automatically after installation:

sudo systemctl status apache2
Output confirmed active (running) status.

📸 Screenshot: Terminal showing Apache2 active (running) in green

Step 6: Verify Default Apache Page
Opened a browser and navigated to the server's public IP address:

http://20.84.74.103
The default Apache Ubuntu welcome page loaded successfully, confirming the web server was live and accessible from the internet.

📸 Screenshot: Browser showing Apache2 default "It works!" page

Step 7: Deploy Custom HTML Page
Replaced the default Apache page with a custom HTML webpage using the tee command:

sudo tee /var/www/html/index.html > /dev/null << 'EOF'
<!DOCTYPE html>
<html>
<head>
 <title>My Azure VM Website</title>
</head>
<body>
 <h1>Hello World! I'm Maurrin Carter - Welcome to My Page!</h1>
 <p>This website is hosted on an Azure Virtual Machine running Apache on Ubuntu.</p>
</body>
</html>
EOF
Restarted Apache to apply changes:

sudo systemctl restart apache2
📸 Screenshot: Terminal showing the tee command deploying the custom HTML file

Step 8: Confirm Live Custom Website
Refreshed the browser at http://20.84.74.103 and confirmed the custom page loaded successfully.

📸 Screenshot: Browser displaying "Hello World! I'm Maurrin Carter - Welcome to My Page!"

Results
A fully functional Linux web server running on Microsoft Azure now serves a custom HTML webpage accessible from any browser via public IP. This project demonstrates end-to-end cloud infrastructure deployment from VM provisioning through live web application delivery.

Key Takeaways
Azure makes cloud VM provisioning fast and repeatable
Apache2 installs and activates quickly on Ubuntu with minimal configuration
NSG rules control all inbound and outbound traffic to the VM
The /var/www/html/ directory serves as Apache's default web root
SSH gives full remote command line control of cloud infrastructure
Next Steps
Register a custom domain name and point it to this server
Configure HTTPS using Let's Encrypt SSL certificate
Build out a full portfolio website on this VM
Explore Azure Load Balancer and auto-scaling
