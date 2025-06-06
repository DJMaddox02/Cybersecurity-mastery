# Lab: Detecting and Preventing Brute-Force Attacks Using Fail2Ban
- Date Completed: 5/15/2025
- Skills: Log analysis, brute-force detection, Fail2Ban setup
- Enviornment: Ubuntu Linux

## Project Description
Brute-force attacks involve repeatedly guessing passwords (e.g., via SSh login attempts). In this lab, I detected brute-force activity in system logs and implemented **Fail2Ban** to automatically block attackers after multiple attempts.

## Objectives 
- Analyze Linux logs to detect brute-force login attempts
- Set up Fail2Ban to protect SSH
- Create custom jail rules
- Verify that malicious IPs are blocked automatically

## Detection: Review Failed SSH Logins
### 1. View Failed Login Attempts
```bash
grep "Failed Password" /var/log/auth.log
```
Example output:
```bash
Jun 5 12:22:33 server sshd[4001]: Failed password for invalid user admin from 192.168.1.22 port 4455 ssh2
Jun 5 12:22:35 server sshd[4001]: Failed password for root from 192.168.1.22 port 4455 ssh2
```
- Repeated failed login attempts indicate a brute-force attack

## Prevention: Install and Configure Fail2Ban
### 2. Install Fail2Ban
```bash
sudo apt update
sudo apt install fail2ban
```

### 3. Create a Local Jail Config File
```bash
sudo cp /etc/fail2ban/jail.config /etc/fail2ban/jail.local
```
Edit the file:
```bash
sudo nano /etc/fail2ban/jail.local
```

### 4. Configure the SSH Jail
Under [sshd] section, ensure the following:
```ini
enabled = true
port = ssh
logpath = /var/log/auth.log
maxretry = 5
bantime = 3600
findtime = 600
```
- blocks IPs that fail login 5 times in 10 minutes, for 1 hour

### 5. Restart and Enable Fail2Ban
```bash
sudo systemctl restart fail2ban
sudo systemctl enable fail2ban
```

### 6. Check the Status of SSH Jail
```bash
sudo fail2ban-client status sshd
```
- See how many IPs are currently banned

### 7. View Banned IPs
```bash
sudo iptables -L
```
- Shows IPs that were dropped or rejected by Fail2Ban

# Summary
In this lab what I did:
- Analyzed auth.log to detect brute-force attempts via SSh
- Installed and configured Fail2Ban to respond automatically
- Created jail rules to ban offending IPs
- Improved system resilience to one of the most common cyberattacks

# Tools Used
- Linux CLI
- grep for log analysis
- Fail2ban (open-source intrusion prevention)
- SSH brute-force detection rules
