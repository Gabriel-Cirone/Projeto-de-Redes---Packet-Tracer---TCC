🌐 Corporate Network Project with Client and IoT Integration


📌 Overview


This project simulates a complete corporate network infrastructure using Cisco Packet Tracer, featuring departmental segmentation, dynamic routing, network services and communication with an external client integrated with IoT devices. With the aim of automating farm management processes, IoT can improve animal welfare and also save time for owners.


The architecture follows the hierarchical network model:


Access Layer Distribution Layer Core Layer (Routing) WAN Connectivity (ISP)


🏢 Network Structure (Company)


The network has been segmented using VLANs to logically separate the departments:


Department VLAN Subnet


IT 10 192.168.1.0/25, Administration/Sales 20 192.168.1.128/25, HR and Marketing 30 192.168.2.0/25, Servers 40 192.168.2.128/25.


🔀 VLANs (Virtual LAN)


VLANs were used for:


Traffic isolation Reduction of broadcast traffic Organisation by department Improved security Basic configuration: Access ports → end devices Trunk ports → communication between switches


🔄 Inter-VLAN Routing


Performed via multilayer (Layer 3) switches, enabling communication between different VLANs.


Example:


interface vlan 10 ip address 192.168.1.1 255.255.255.128


🌐 Core and WAN Routing


Routers used:


R1 (Core) R2 (Core) R3 (Client) Features: Point-to-point links using /30 subnets Communication via ISP Path redundancy


📡 Routing Protocol – OSPF


OSPF (Open Shortest Path First) was implemented for:


Automatic route discovery High availability Fast convergence Benefits: Automatic failover Scalability Reduced manual configuration


🌍 Communication with the Client


Communication flow:


Company → R1/R2 → ISP → R3 → Client Network


🏠 Client Network Subnet: 192.168.20.0/25 Devices: PCs Printer Local switch


📡 IoT Integration


The client has connected IoT devices:


Temperature sensor Humidity sensor Smoke sensor Presence/light sensor


Features: Remote monitoring Wireless network communication Smartphone control


📥 DHCP (Dynamic Host Configuration Protocol)


Responsible for automatically providing:


IP address Default gateway DNS server Benefits: Automation Prevents IP conflicts Simplifies administration


🌐 DNS (Domain Name System)


DNS server configured for name resolution on the network.


📍 Configuration: DNS IP: 192.168.2.131 Function: www.empresa.com → 192.168.2.131


Allows access by name rather than IP. If you wish, you can test ‘empresa.com’ in the web browser of any company PC and you will be taken to the website!


🖥️ Servers


Located on VLAN 40:


DHCP server DNS/Web server (192.168.2.131) Email server 🔐 Security


Measures implemented:


VLAN segmentation Server separation Broadcast reduction


🚀 Conclusion


This project represents a complete implementation of a modern corporate network, including:


Efficient internal communication Integration with external networks Essential services (DHCP, DNS) Scalability and redundancy Application of real-world concepts


📎 Technologies Used Cisco Packet Tracer, VLAN (802.1Q), OSPF, DHCP, DNS, IoT Simulation.
