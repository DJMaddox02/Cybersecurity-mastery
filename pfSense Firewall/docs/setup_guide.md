# Setup Guide - pfSense Firewall on VirtualBox

## 1. Download Required Software
- **Orical VirtualBox** -> https://www.virtualbox.org/
- **pfSense ISO** -> https://www.pfsense.org/download/
    - When downlaoding pfSense make sure to have these items selected if using a Windows computer
        - **Architecture**: AMD64 (64-bit)
        - **Installer**: CD Image (ISO) Installer
        - **Mirror**: Closest to your location
<img width="1182" height="645" alt="image" src="https://github.com/user-attachments/assets/ef99153f-ddb4-4f91-84fb-14e999ef570c" />

     
## 2. Create a New Virtual Machine 
- open **VirtualBox** -> Click **New**.
- Name: **pfSense-Firewall**
- Type: BSD -> Version: FreeBSD (64-bit).
- Memory: **2048 MB** minimum.
- Disk: **20 GB dynamically allocated**.

## 3. Attach pfSense ISO
- Select VM -> **Settings** -> **Storage**
- Under Controller: IDE -> Click **Empty CD**
- Choose pfSense ISO File.
- Ensure boot order is set to boot from ISO first.

## 4. Configure Network Interfaces
pfSense needs **two NICs:**
- **Adapter 1 (WAN):** Attached to **NAT** (for internet)
- **Adapter 2 (LAN):** Attached to **Internal Network** (for lab machines).

## 5. Install pfSense
- Start VM -> pfSense installer loads.
- Accept license -> Continue with default install.
- Disk partition: **Auto (UFS).**
- After install -> Remove ISO -> Reboot VM

## 6. Initial pfSense Configuration
- On reboot, pfSense assigns interfaces:
    -em0 -> WAN
    -em1 -> LAN (10.0.0.1/24)
- Login at console -> Use default credentials:
    - User: admin
    - Pass: pfsense
- From a LAN-connected VM (e.g., Kali Linux), set
  IP: 10.0.0.1
-Open Browser -> Go to http://10.0.0.1
-Run **Setup Wizard**:
    - Hostname, domain, DNS servers
    - Confugure WAN (DHCP by Default)
    - Confirm LAN IP (keep default for now)
    - Change admin password
