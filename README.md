# Deploying a Linux Web Server on Microsoft Azure

Linux web server deployment on Microsoft Azure using a Virtual Machine and Apache. Provisioned an Azure Linux VM, installed Apache, and deployed a custom HTML webpage via public IP.

* **Author:** Maurrin Carter
* **Date:** August 2, 2026
* **Platform:** Microsoft Azure
* **Difficulty:** Beginner-Intermediate

---

## Project Overview

This project demonstrates how to provision a Linux Virtual Machine on Microsoft Azure, install and configure the Apache web server, and deploy a custom HTML webpage accessible via a public IP address. This project builds core cloud engineering skills including VM provisioning, SSH remote access, Linux package management, and web server configuration.

---

## Technologies Used

* Microsoft Azure (Virtual Machine, Networking, NSG)
* Ubuntu Linux (22.04 LTS)
* Apache2 Web Server
* SSH (Secure Shell)
* HTML
* Nano / Terminal (CLI)

---

## Skills Demonstrated

* Cloud infrastructure provisioning on Azure
* Linux command line navigation
* Remote server access via SSH
* Web server installation and management
* Custom web page deployment
* Network Security Group (NSG) configuration

---

## Step-by-Step Process

### Step 1: Create the Virtual Machine
Provisioned a new Linux Virtual Machine in the Azure Portal with the required configuration.

![VM Deployed](screenshots/project-2/cp2_vm_deployed.png)

---

### Step 2: Configure Network Security Group (NSG)
Added inbound security rules to allow web and remote access traffic (Port 22 for SSH and Port 80 for HTTP).

![VM NSG Configuration](screenshots/project-2/cp2_vm_NSG.png)

---

### Step 3: Connect via SSH
Connected to the virtual machine remotely using PowerShell and verified the SSH name prompt match.

![SSH Connection PowerShell](screenshots/project-2/cp2_vm_sshtovm_powershell.png)
![SSH Login OK](screenshots/project-2/cp2_vm_sshlogin_ok.png)
![SSH Name Prompt Match](screenshots/project-2/cp2_ssh_namepromptmatch.png)

---

### Step 4: Update Package Lists and Install Apache
Updated the local package manager and installed the Apache2 web server on the Ubuntu server.

![Package List Update 1](screenshots/project-2/cp2_vm_%20package%20list_update.png)
![Package List Update 2](screenshots/project-2/cp2_vm_%20package%20list_update_2.png)
![Apache Update 1](screenshots/project-2/cp2_vm_apacheupdate.png)
![Apache Update 2](screenshots/project-2/cp2_vm_apacheupdate_2.png)
![Apache Update 3](screenshots/project-2/cp2_vm_apacheupdate_3.png)

---

### Step 5: Verify Apache is Running
Validated that the Apache service status was active and running.

![Apache Validate](screenshots/project-2/cp2_vm_apachevalidate.png)

---

### Step 6: Verify Default Apache Page
Opened a browser and navigated to the server's public IP address to view the default Ubuntu page.

![Apache Ubuntu Default Page](screenshots/project-2/cp2_vm_apache_ubuntu_defaultpage.png)

---

### Step 7: Deploy Custom HTML Page
Used custom HTML commands and terminal editing to replace the default page.

![Custom HTML Command](screenshots/project-2/cp_2_%20Custom%20HTML%20Command.png)
![VM Validation Pass](screenshots/project-2/cp2_vm_validationpass.png)

---

### Step 8: Confirm Live Custom Website
Refreshed the browser to confirm the custom web application rendered successfully.

![Live Custom Website](screenshots/project-2/cp2_Live%20Custom%20Website.png)

---

## Results

A fully functional Linux web server running on Microsoft Azure now serves a custom HTML webpage accessible from any browser via public IP. This project demonstrates end-to-end cloud infrastructure deployment from VM provisioning through live web application delivery.

---

## Screenshot References

Here is the complete master list of all 15 project screenshots formatted for your repository:

![Live Custom Website](screenshots/project-2/cp2_Live%20Custom%20Website.png)
![SSH Name Prompt Match](screenshots/project-2/cp2_ssh_namepromptmatch.png)
![Package List Update](screenshots/project-2/cp2_vm_%20package%20list_update.png)
![Package List Update 2](screenshots/project-2/cp2_vm_%20package%20list_update_2.png)
![VM NSG](screenshots/project-2/cp2_vm_NSG.png)
![Apache Ubuntu Default Page](screenshots/project-2/cp2_vm_apache_ubuntu_defaultpage.png)
![Apache Update](screenshots/project-2/cp2_vm_apacheupdate.png)
![Apache Update 2](screenshots/project-2/cp2_vm_apacheupdate_2.png)
![Apache Update 3](screenshots/project-2/cp2_vm_apacheupdate_3.png)
![Apache Validate](screenshots/project-2/cp2_vm_apachevalidate.png)
![VM Deployed](screenshots/project-2/cp2_vm_deployed.png)
![SSH Login OK](screenshots/project-2/cp2_vm_sshlogin_ok.png)
![SSH to VM PowerShell](screenshots/project-2/cp2_vm_sshtovm_powershell.png)
![VM Validation Pass](screenshots/project-2/cp2_vm_validationpass.png)
![Custom HTML Command](screenshots/project-2/cp_2_%20Custom%20HTML%20Command.png)

---

## Key Takeaways

* Azure makes cloud VM provisioning fast and repeatable.
* Apache2 installs and activates quickly on Ubuntu with minimal configuration.
* NSG rules control all inbound and outbound traffic to the VM.
* The `/var/www/html/` directory serves as Apache's default web root.
* SSH gives full remote command line control of cloud infrastructure.

---

## Next Steps

* Register a custom domain name and point it to this server.
* Configure HTTPS using a Let's Encrypt SSL certificate.
* Build out a full portfolio website on this VM.
* Explore Azure Load Balancer and auto-scaling.
