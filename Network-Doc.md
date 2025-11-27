<div align="center">

# Home Network Documentation

</div>

## Physical Topology
### Device Details:
 * **Device Locations:** Router in the Sitting Room, desktop PC in Room1, Laptop in Room2, Tablet in Room3, Smart Phone in Room4
 * **Connection Type:** Connection is wireless (Wi-Fi ).
 * **Cable Runs:** Fiber Optics from Internet to Router.
## Logical Topology
<img width="975" height="548" alt="image" src="https://github.com/user-attachments/assets/f6c76d37-de7f-4e88-9bd9-af05dfe1e5cd" />

### Network Devices and Services

|**Device Name**|**Type**|**Make/Model**|**Physical Location**|**IP Address**|**MAC Address**|**Firmware Version**|
|------|-----|-----|-----|-----|----|----|
|EdgeRouter|Router|ISP-ABC-Model|Main Floor Closet|192.168.1.254|A1:B2:C3:D4:E5:F6|v1.2|
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
