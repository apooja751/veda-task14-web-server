# Task 14: Install a Web Server on a Cloud VM

## Internship
**Organization:** Veda Technology  
**Track:** Cloud Computing Internship  
**Task:** Task 14 — Install a Web Server on a Cloud VM

## Aim
To install and configure a web server on a cloud virtual machine and host a custom HTML webpage accessible through the VM's public IP address.

## Objective
To understand how cloud compute instances can host web applications using a Linux operating system and a web server.

## Tools and Technologies
- Amazon Web Services (AWS EC2)
- Ubuntu Server 26.04 LTS
- Nginx Web Server
- HTML and CSS
- SSH
- Windows PowerShell
- GitHub

## Cloud Configuration
- **AWS Region:** Asia Pacific (Mumbai) — `ap-south-1`
- **Instance Name:** `veda-task14-web-server`
- **Instance Type:** `t3.micro`
- **Operating System:** Ubuntu Server 26.04 LTS
- **Web Server:** Nginx
- **Web Root:** `/var/www/html/`
- **HTML File:** `/var/www/html/index.html`

## Implementation Steps

### 1. Launch the EC2 Instance
Created an Ubuntu EC2 virtual machine in the Mumbai region and enabled a public IP address.

### 2. Configure Network Security
Configured the security group with these inbound rules:
- SSH — TCP port 22, restricted to My IP.
- HTTP — TCP port 80, allowed from anywhere over IPv4 to make the website publicly accessible.

### 3. Connect Using SSH
Connected to the Ubuntu instance from Windows PowerShell using the EC2 private key.

### 4. Update Package Information
```bash
sudo apt update
```

### 5. Install Nginx
```bash
sudo apt install nginx -y
```

### 6. Verify the Nginx Service
```bash
sudo systemctl status nginx
```

Confirmed that the Nginx service was active and running.

### 7. Create the Custom Webpage
Created a custom HTML page at `/var/www/html/index.html` containing a Veda Technology heading, internship information, and deployment details.

### 8. Verify the Web Server
```bash
curl -I http://localhost
```

The server returned `HTTP/1.1 200 OK`, confirming that Nginx was serving the HTML content successfully.

### 9. Access the Website
Opened the EC2 public IPv4 address in a browser using HTTP and verified that the custom webpage loaded successfully.

## Screenshots
Screenshots documenting the instance configuration, network security, running instance, SSH connection, Nginx status, public webpage, and HTTP verification are included in the `screenshots/` directory.

## Result
Successfully installed and configured Nginx on an AWS EC2 Ubuntu virtual machine and hosted a custom HTML webpage that was accessible through the instance's public IP address.

## Learning Outcomes
- Learned to launch and configure a cloud virtual machine.
- Practiced connecting to Ubuntu using SSH.
- Learned to install and verify a Linux web server.
- Understood how security groups control HTTP and SSH access.
- Hosted and tested a custom HTML webpage on AWS EC2.

## Cleanup and Cost Management
After capturing the required evidence, stop or terminate the EC2 instance when it is no longer needed. Termination deletes the instance and its instance-store data; review attached storage and other billable resources separately before cleanup.

**Note:** Never upload private SSH keys, AWS credentials, or other secrets to GitHub.
