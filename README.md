# 🖧 Small Office Network Simulation — VLAN Segmentation Project  

## 🔹 Project Overview  
This project simulates a **Small Office Network** using Cisco Packet Tracer.  
It contains **four isolated departments (VLANs)** connected through a **Core Switch**, with VLAN segmentation and trunking implemented professionally.  
Each department communicates only within its own VLAN, providing both **security and traffic separation**.

---

## 🏢 Network Topology  

| Department | VLAN ID | IP Range | Switch | PC Count |
|-------------|----------|-----------|----------|-----------|
| Human Resources (HR) | 10 | 192.168.10.0/24 | SW-HR | 10 |
| IT Department | 20 | 192.168.20.0/24 | SW-IT | 10 |
| Sales | 30 | 192.168.30.0/24 | SW-SALES | 10 |
| Management | 40 | 192.168.40.0/24 | SW-MGMT | 10 |
| Core Switch | - | 192.168.99.0/24 | SW-CORE | - |
| Router | - | 192.168.99.1/24 | R1 | - |

---

## ⚙️ Devices Used
- **1× Router:** Cisco 2811  
- **1× Core Switch:** Cisco 2960  
- **4× Access Switches:** Cisco 2960  
- **40× PCs (10 per department)**  

---

## 🧠 Design Principles
- Each department is isolated using **VLANs** (10, 20, 30, 40).  
- The Core Switch manages **all VLAN definitions** and **trunk links**.  
- **No inter-VLAN routing** (each VLAN is isolated).  
- **Secure management configuration** (password encryption, banners).  
- Optimized configuration — no unnecessary commands.

---

## 🟦 Core Switch (SW-CORE)
```bash
enable
conf t

! VLAN Definitions
vlan 10
 name HR
vlan 20
 name IT
vlan 30
 name SALES
vlan 40
 name MANAGEMENT
vlan 99
 name MGMT
exit

! Trunk Links to Access Switches
interface range FastEthernet0/1 - 0/4
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30,40,99
 no shutdown
exit

! Management VLAN Interface
interface vlan 99
 ip address 192.168.99.1 255.255.255.0
 no shutdown

! Security Settings
service password-encryption
enable secret core123
banner motd #Unauthorized access is prohibited#
line console 0
 password cisco
 login
exit

spanning-tree mode pvst
end
wr
