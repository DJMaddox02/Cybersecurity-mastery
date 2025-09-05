# Custom Rules & Explinations

## pfSense Firewall Rule: Block LAN to WAN Access
This guied doccuments how to configure a firewall rule in **pfSense** that blocks access from LAN clients to services on the WAN interface.
---

## Objective
Prevent any devices on the **LAN Subnet** from accessing services hosted on th **WAN Subnet**

## Rule Configuration
| Setting              | Value                             |
|----------------------|-----------------------------------|
|**Action**            | Block                             |
|**Interface**         | LAN                               |
|**Address Family**    | IPV4+IPV6                         |
|**Protocol**          | Any                               |
|**Source**            | LAN net (all LAN subnets)         |
|**Destination**       | WAN net (all WAN subnets)         |

---
## Steps to Configure
1. **Log in pfSense web GUI**
     - Open a browser and navigate to your firewall IP
     - Enter credentials
2. **Navigate to firewall rules**
     - GO to **Firewall > Rules**
     - Select the **LAN** tab
3. **Add New Rule**
     - Click **Add (+)** to create new rule
4. **Configure Rule Parameters**
     - **Action:** `Block`
     - **Interface:** `LAN`
     - **Address Family:** `IPV4+IPV6`
     - **Protocol:** `Any`
     - **Source:** `LAN net`
     - **Destination:** `WAN net`
5. **Add Description**
   ```text
   Block LAN clients from accessing WAN services
   ```
6. **Save & Apply**
     - Click **Save**
     - Click **Apply Changes** at the top of page.
