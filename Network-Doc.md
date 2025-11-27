<div align="center">

# Home Network Documentation

</div>

## Physical Topology
### Device Details:
 * **Device Locations:** Router in the Sitting Room, Desktop PC in Room1, Laptop in Room2, Tablet in Room3, Smart Phone in Room4
 * **Connection Type:** Connection is wireless (Wi-Fi ).
 * **Cable Runs:** Fiber Optics from Internet to Router.
## Logical Topology
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f6c76d37-de7f-4e88-9bd9-af05dfe1e5cd" />

### Network Devices and Services

|**Device Name**|**Type**|**Make/Model**|**Physical Location**|**IP Address**|**MAC Address**|**Firmware Version**|**Default Gateway**|
|------|-----|-----|-----|-----|----|----|----|
|EdgeRouter|Router|ISP-ABC-Model|Sitting Room|192.168.1.254|A1:B2:C3:D4:E5:F6|v1.2|
|Dell-PC	|PC	|Workstation|Room1|192.168.1.60|D3:E4:A8:B7:F3|  |192.168.1.|254
|ASUS TUF-Laptop|Gaming Laptops |A15 -ASUS Laptop|Room2|192.168.1.65|A3:C5:F4:A9:D2:F8| |192.168.1.254|
|Lenovo-Tablet|Smart Tablet|X5- Lenovo Tablet|Room3|192.168.1.70|B3:C5:F4:A9:C2:D8| |192.168.1.254|
|Samsung Phone|Mobile Phone|Smart Phone|Room4|192.168.1.75|B6:E5:F4:A9:C2:D7| |192.168.1.254|

### Servers/Services
| **Service**|**Server/Device**|**Protocol(s)**|**Port(s)**|**Internal Access URL** |
|----|---|---|---|------|
|DHCP|EdgeRouter|UDP|67, 68|N/A |
|DNS (Internal| NAS-Server (Pi-Hole)|UDP|53|192.168.1.50|
|File Share (SMB)|NAS-Server|TCP|445|smb://NAS-Server|
|VPN (Inbound)|Router/Firewall|TCP/UDP|1194|vpn.myhomedomain.com|

### Addressing Documentation
This section defines your IP address structure and allocation rules.
#### IP Addressing Scheme
* **ISP Connection (WAN):** DHCP (Dynamic IP from ISP)
* **Internal Network (LAN):** 192.168.1.0/24
  * **Subnet Mask:** 255.255.255.0
  * **Default Gateway (Router IP):** 192.168.1.254
  * **DHCP Pool:** 192.168.1.100 to 192.168.1.199
  * **Static IP Range:** 192.168.1.2 to 192.168.1.99 (Reserved for servers, access points, and persistent devices).

#### Static IP Address Assignments
|**Device**|**Assigned IP**|**Purpose**|
|---|---|---|
|NAS-Server|192.168.1.50|File storage, media streaming, DNS|
|Desktop-PC |192.168.1.60|Workstation, specific port forwarding|
|Laptop| 192.168.1.65| Personal Computer, for everyday internet exploration|
|Tablet| 192.168.1.70| for making call and internet exploration|
|Smart Phone| 192.168.1.75| for making call and internet search|

### Device Configurations
* **Router:**
  * DHCP range: 192.168.1.100–192.168.1.200
  * VLANs configured for segmentation
  * WPA3 Wi-Fi security enabled
* **NAS Server:**
    * RAID 1 for redundancy
    * SMB shares for PCs
    * Scheduled backups nightly
* **PCs:**
    * Static IPs for reliability
    * Windows Server tools installed for labs
* **IoT Devices:**
    * Isolated VLAN for security

### Secure Credential Storage
* **Password Manager** (e.g., Bitwarden, KeePass) used for all device logins
* **Multi-Factor Authentication (MFA)** enabled on router and NAS
* **SSH Keys** stored securely for NAS administration
* **No plaintext storage** of credentials in documentation
