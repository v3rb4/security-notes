# Network Fundamentals

## Network Layer 
- The Network Layer (Layer 3) of the OSI model is resondible for logical addressing, routing, and forwarding data packets between devices across different networks.
- It's primary goal is to determine the optimal path for data to travel from the source to the destination, even if the divices are on separate networks.
- The nework layer abstracts the underlying physical network, allowing for the creation of a cohesive internetwork.
## Network Layer Protocols
- Internet Protocol
- Internet Corntrol Message Protocol (ICMP)
1. IP operates at the network layer (Layer 3) of the OSI model and is responsible for logical addressing, routing, and the fragmentation and reassembly of data packets.
2. IP enables communication between devices on different networks by providing a standardized way to identify and locate hosts.

## IP Header Format
- IP Source Address - packet source
- IP Destination Address - packet destination
- Time-to-Live (TTL) - An 8 bit value that indicates the ramaining life of the packet
- Type-of-Serice (ToS)
- Protocol
## IPv4 Header Fields
- version 4 bits
- Header length 4 bits
- Type of Service 8 bits
- total Length 16 bits
- Identefication 16 bits
- flags 3 bits
- Time-to-Live (TTL 8 bits)
- Protocol 8 bits
- Source IP address 32 bits
- Destination IP Adress 32 bits

## Transport Layer
- ensures reliable, end to end communication, handling tasks such as error detection, flow control, and segmentation of data into smaller units
- responsible for providing end to end communication and ensuring the reliable and ordered delivery pf data between two devices on a network.

## Transport layer protocols
1. TCP (Transmission Control Protocol): connection oriented protocol providing reliable and ordered data delivery.
2. UDP (User Data Protocol): Connectionless protocol that is faster but provides no guarantees regarding the order or reliability of data delivery.

## TCP 3-Way Handshake
1. SYN (Synchronize): The process begins with the client sensing a TCP segment with the SYN flag set. The initial message indicates the client's intention o establish a connection andm includes an initial sequence number (ISN), which is arandomly chosen value.
2. SYN-ACK: Upon receicing the SYN segment, the server responds with a TCP segment that holds both the SYN and ACK flags set. The ACK number is set to one more the initial sequence number received in the clients SYN segment. The server also generates its own sequence number.
3. ACK: Finally the client ackmowleges the server's response by sending a TCP segment with the ACK flag set. The acknowlegment number is set to one more that the server's initial sequence number. 

## Network Mapping 
- Network mapping is the process of discovering and identifying devices, hosts, and network infrastructure within a target network. It helps penetration testers understand the network’s layout, detect active hosts, open ports, and running operating systems, and identify potential entry points for further exploitation.

## Network Mapping Objectives
- Network Mapping Objectives:
	1.	OS Fingerprinting – Identifying operating systems on discovered hosts to target specific vulnerabilities.
	2.	Service Version Detection – Determining versions of services running on open ports to find potential exploits.
	3.	Identifying Security Measures – Detecting firewalls, intrusion prevention systems, and other defenses to plan attacks accordingly.

## Host Discovery Techniques
	1.	Ping Sweeps (ICMP Echo Requests) – Sending ICMP pings to identify live hosts.
	2.	ARP Scanning – Using ARP requests to detect hosts on a local network.
	3.	TCP SYN Ping (Half-Open Scan) – Sending SYN packets to check for active hosts stealthily.
	4.	UDP Ping – Sending UDP packets to detect hosts that don’t respond to ICMP or TCP.
	5.	TCP ACK Ping – Sending ACK packets; a TCP RST response indicates a live host.
	6.	SYN-ACK Ping – Sending SYN-ACK packets; a TCP RST response confirms host activity.







