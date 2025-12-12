**🎓 University Campus Network – Cisco Packet Tracer (Semester 4 Project)**

A professionally designed campus-wide network implementing VLANs, routing, security, and core networking principles using Cisco Packet Tracer.

**📁 Project Files**
**File	Description**
| File | Description |
|----------|----------|
| Campus_Network.pkt    | Complete Cisco Packet Tracer project   |
| configs/    | Running-configs of all routers & switches     |
| ip_plan.csv    | IP addressing scheme   |
| topology.png    | Network topology diagram     |
| test_cases.md    | Connectivity & verification tests   |
| README.md    | Documentation (this file)     |

**🏫 1. Project Overview**

This project simulates a university-wide network using a hierarchical architecture:

🔹 Core Router → College Router / Hostel Router → APs & End Devices

✅ Key Features

* Separate networks for Hostel, Academic, Library, IT Consulting, and Server Center

* Wireless networks with APs across all buildings

* Inter-router static routing for communication between blocks

* Centralized servers (Email, DNS, Web) in Server Center

* DHCP-enabled host assignment

* ACL-based security

* Realistic default gateway configurations per building

**🗺️ 2. Network Topology**
**Topology includes:**

🟦 Main Router (1941) – Core of the entire campus

🟩 College Router (1941) – Handles Academic / Dome / Library networks

🟧 Hostel Router – Connects Boys & Girls hostel blocks

🟪 Server Center – Email server, DNS server, Web server

🟨 Access Points – Wireless connectivity in each block

🖥️ End Devices – PCs, Laptops, Smartphones

**🧩 3. Device Inventory**
* Device	Type	Role
* Main Router	1941 Router	Core router of campus
* College Router	1941 Router	Academic & Dome building gateway
* Hostel Router	Router/Switch	Boys & Girls block gateway
* Switch-ServerCenter	2960 Switch	Connects Email, DNS, Web servers
* Server-EMAIL	Server	Email service (192.168.2.2)
* Server-DNS	Server	DNS service (192.168.2.3)
* Server-WEB	Server	Web hosting (192.168.2.4)
* Wireless APs	Access Points	Wi-Fi networks in all blocks
* End Devices	PCs, Laptops, Smartphones	Students & staff devices
  
**🌐 4. IP Addressing Plan**
* Area / Building	Network	Gateway	Example IPs
* Academic Blocks (AB1, AB2)	192.168.1.0/24	192.168.1.1	.2 – .15
* Library / Dome / IT Consulting	192.168.1.0/24	192.168.1.1	.4, .5, .6, .7
* Server Center	192.168.2.0/24	192.168.2.1	Email: .2, DNS: .3, Web: .4
* Hostel Blocks (Boys/Girls)	192.168.3.0/24	192.168.3.1	Phones & PCs: .2 – .9
  
**📡 Wireless Password**

1234567890

**🔐 Router Passwords**
* Router	Console Password	SSH Password
* Main Router	cisco	admin
* College Router	muj@123	admin
* Hostel Router	muj@123	admin
  
**🛰️ 5. Sample Switch Configuration (Access Points & Blocks)**
* **vlan 10**
 name Academic

* **vlan 20**
 name ServerCenter

* **vlan 30**
 name Hostel

* **interface gi0/1**
 switchport mode trunk
 switchport trunk allowed vlan 10,20,30

**🚦 6. Inter-VLAN / Inter-Block Routing**

**Main Router Interfaces (Example)**

* **interface g0/0**
 ip address 192.168.2.1 255.255.255.0   # Server Center

* **interface g0/1**
 ip address 192.168.1.254 255.255.255.0 # To College Router

* **interface g0/2**
 ip address 192.168.3.254 255.255.255.0 # To Hostel Router

**🔐 7. ACL Security Example (Optional Enhancement)**

* ip access-list extended BLOCK_HOSTEL_TO_SERVER

* deny ip 192.168.3.0 0.0.0.255 192.168.2.0 0.0.0.255
 
* permit ip any any

**🖥️ 8. Server Configuration**
* Email Server

* **IP:** 192.168.2.2

* DNS Server

* **IP:** 192.168.2.3

**Example Entry:**
* university.local → 192.168.2.4

* Web Server

* **IP:** 192.168.2.4

**🧪 9. Verification & Testing**
* Test	Command	Expected Result
* Ping gateway	ping 192.168.1.1	Replies (PCs in Academic Block)
* Ping Server Center	ping 192.168.2.2	Email server reachable
* DHCP Check	ipconfig	Auto IP assigned
* Web Test	Browser → 192.168.2.4	Webpage appears
* DNS Test	nslookup university.local	Returns 192.168.2.4
  
**📤 10. Exporting Device Configurations**

8 Click device → CLI

**Enter:**

* enable
* show running-config


**Copy & save to:**

**configs/**

   Main-Router.txt
   
   College-Router.txt
   
   Hostel-Router.txt
   
   Switch-Server.txt

**📝 11. Submission Checklist**

✔ .pkt file added

✔ README updated

✔ topology screenshot added

✔ IP plan completed

✔ Device configs uploaded

✔ Testing completed

✔ Passwords & server IPs documented
