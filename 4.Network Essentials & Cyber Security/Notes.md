## 4.1 Introduction to Networks for Data Engineers

### Objectives

- Explain the principles of computer networks, including IP addressing, TCP/IP and the OSI model.
- Demonstrate awareness of modern networking practices.
- Learn about network infrastructure costs and sustainability.
- Explain the role of different types of network devices.

**1. Basics principles of networks**

- Routing & Switching
- Security Appliances & Firewalls
- VoIP & Unified Communications
- Wireless
- IPSec & SSL VPN
- Quality of Service (QoS)

**2. Common network services**

Hub
• Multiport repeater
Switch
• Collision domains
• MAC address learning
Router
• Broadcast domains
• ‘Gateway’
Firewall
• Stateful packet inspection
VPN concentrator
• VPN termination point

**3. Networking models**

Peer to peer
- print sharing
- file sharing

Client/Server

Email 
- Email server runs email server software.
- Clients use client software to access email.
 
Web
- Web server runs web server software.
- Clients use browser software to access web pages.

File 
- File server stores corporate and user files.
- The client devices access these files.

**4. Network components**

Media Types 
- Metal wires within cables - Uses electrical impulses
- Glass or plastic fibers within cables (fiber-optic cable) - Uses pulses of light
- Wireless transmission  - Uses modulation of specific frequencies of electromagnetic waves.

**5. Network LAN Topologies**

-Physical vs logical topologies

**6. IP Addresses**

- An identifier for a computer or device on a TCP/IP network.
- 99% of the world still use IP version 4 (IPv4) e.g. 192.168.0.1
- Addresses are 32 bits and not assigned by geographic region.
- IP version 6 is newer, uses 128-bit addresses, but adopted slowly due to compatibility issues.
E.g. 1080:0000:0000:0000:0800:0000:417A

IP Addressing (IPv4)

- An IPv4 address is four bytes (octets). Total 32 bits.
- Each byte is a number from 1 to 254 (0 and 255 are special)
- Stored in Big Endian order
- Written in dotted notation, e.g. 192.168.21.76

Hexadecimal

**7. Network topology architectures**
- Spine Leaf Architecture
- Three and two-tier architectures

**8. Redundancy and high availability**

**9. Data Centres**

- Data centres contain aisles, with each aisle containing rows of cabinets.
- Each cabinet contains multiple rack servers.

Data Centre Equipment
- To ensure a reliable uninterrupted supply of power, typically a data centre would use backup generators in case of a power outage…
- However, these can take a few minutes to come online, so in the meantime..
...  a large set of batteries keep critical systems running for long enough to either shutdown properly, or transition to the power supplied by the generator.

**10. Distributed data products**

- Clients send heartbeats to the server every three seconds
- After a period with no heartbeats, a client is marked as lost
- Data recovery will kick in
- A client can rejoin the cluster at any time
- Alternatively, whitelists can be created by administrators to control which worker hosts are allowed
- Similarly, blacklists can be created

**11. Modern networking practices**

Virtual network components
- Virtual network
- Can be created to consist solely of virtual machines on a physical server
- Most networks combine physical and virtual elements
  
**12. Virtual Local Area Networks**

Reasons for using VLANs:
- Separating groups of users who need special security or network functions
- Isolating connections with heavy or unpredictable traffic patterns
- Identifying groups of devices whose data should be given priority handling
- Containing groups of devices that rely on legacy protocols incompatible with the majority of the network’s traffic
- Separating a large network into smaller subnets

**13. VLANs and trunking**

- Trunk
➢A single physical connection between switches through which many logical VLANs can transmit and receive data

- A port on a switch is configured as either an access port or a trunk port
➢Access port - used for connecting a single node
➢Trunk port - capable of managing traffic among multiple VLANs

**15. Understanding network costs**

- Capital Expenditure (CapEx): Initial costs for network hardware like routers, switches, servers, and cabling.
- Operational Expenditure (OpEx): Ongoing costs including power consumption, maintenance, and network management.

TCO
Total Cost of Ownership encompasses all the direct and indirect costs associated with the acquisition, deployment, operation, and maintenance of network resources over their lifecycle.

- Hardware and Software Acquisition: Costs of purchasing network equipment and software licenses.
- Installation and Configuration: Expenses involved in setting up and configuring network hardware and software.
- Maintenance and Upgrades: Ongoing costs for maintaining, updating, and upgrading network systems to ensure efficiency and security.
- Training and Support: Costs related to training staff to operate and manage network systems and ongoing technical support.
- Energy Consumption: Operational costs for electricity which can be significant in data centres and network operations.

Other cost factors
- Software Licenses: Expenses related to network management and security software.
- Manpower: Costs of hiring qualified IT staff for network setup, management, and troubleshooting.
- Downtime and Risk Costs: Financial impact associated with network downtimes, including loss of productivity and potential breach risks.

**16. Strategies to reduce cost**

- Energy Efficiency: Investing in energy-efficient hardware to reduce power consumption.
- Virtualisation: Using virtual machines and software-defined networking to optimise resource usage.
- Cloud Services: Outsourcing certain network functions to cloud providers to reduce on-premises hardware needs.
- Preventative Maintenance: Regular maintenance to prevent costly downtime and repairs.
- Data compression: Reducing the size of data to save storage space and decrease transmission times.

Transfer optimisation

- Caching: Storing copies of frequently accessed data closer to the user to reduce data retrieval times and bandwidth usage.
- Load Balancing: Distributing network traffic across multiple servers to optimize resource use and minimise response times.
- Traffic Shaping: Prioritising certain types of data to ensure critical applications have the bandwidth they need.
- Benefits: Enhanced user experience, reduced server load, and minimized energy consumption due to efficient data handling.

**17. Network sustainability - terms**

- Sustainability Concerns: Environmental impact of network operations, particularly energy usage and electronic waste.
- Green Networking: practices and technologies that reduce the environmental footprint of network infrastructure.
- Net-zero emissions: the balance between the amount of greenhouse gas emissions produced and the amount removed from the atmosphere.



