# Lab: Setting Up and Configuring a Firewall
- Date Completed: 2/24/2025
- Skills: Network Security, access control. UFW, system hardening
- Enviorment: Ubuntu 20.04+

## Project Description
In this lab, I configured a firewall using **UFW (Uncompleted Firewall)** on Ubuntu to protect a Linux server. UFW is a user-friendly interface to manage 'iptables', which controls inbound and outbound traffic on a system.

## Objectives 
- Enable and configure a basic firewall
- Allow only necessary services (e.g., SSH, HTTP)
- Block unnecessary ports
- Check status and manage rules
- Secure the system before deployment or exposure to the internet

## Step-by-step: Firewall Setup with UFW
### 1. **Check UFW Status**
```bash
sudo ufw status verbose
```
- Check if UFW is active or inactive.

### 2. Set Default Policy to Deny All Incoming Traffic
```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
- Block all inbound connections by default.
- Allow all outbound connections.

### 3. Allow Specific Services
```bash
sudo ufw allow 22
sudo ufw allow 80
sudo ufw allow 443
```
- Only allow what you need. For example, just port 22 for SSH if you're hardening an internal server.

### 4. Enable UFW 
```bash
sudo ufw enable
```
- Activates the firewall with the rules set above.

### 5. Verify Rules
```bash
sudo ufw status numbered
```
- Shows numbered list of rules currently active.

### 6. Delete a Rule (Optional)
```bash
sudo ufw delete [rule_number]
```
- Removes a specific rule if needed.

### 7. Deny a Specific IP Address (Optional)
```bash
sudo ufw deny from 192.168.1.25
```
- Block access from a known malicious IP.

## Summary 
I configured UFW to block all unauthorized inbound traffic and allow only critical services (like SSH and HTTP). This setup helps minimize the attack surface and enforce principle of least privilege at the network level.
This is an essentail part of:
- System hardening
- Threat mitigation
- SOC analyst responsibilities (especially during response and triage)

## Tools Used
- UFW (Ubuntu's Uncomplicated Firewall)
- Linux CLI
- Basic understanding of ports and protocols (SSH, HTTP, etc.)
