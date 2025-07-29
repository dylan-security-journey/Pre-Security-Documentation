## What is Networking? 

Devices connected together

## Internet

Tim-Berners-Lee (WWW)

Small networks make up internet, small networks also private networks, public networks connect small networks, Two types of networks

## Identifying Devices

Two Identifications

IP address: 4 octets 

Media Access Control (MAC) Address (serial number)

Ex IP. (192.168.1.1) (0-255)

Public Address to identify on internet

Private Address to identify amongst other devices

ISP = Internet Service Provider gives public IP

## IPv6

IPv4 only has 2^32 (4.29B) (Ex. 86.157.52.21)

IPv6 2^128 (340T) (more) (Ex. 2a00.22C4.a531.c500) (8 octets)

## Mac Addresses 

Network interface assigned 12 number, colons = separators, first six represent company, last six is unique number

Spoofing: pretending someone else MAC address

## Ping

ICMP = Internet Control Message Protocol, Used to determine connection or if it exist, measured by echo packet and echo reply

## Star Topology 

Devices connected to central like switch or hub, more expensive because buy cable and equipment, more scalable due to ease of adding devices, more scaling = more maintenance = more downtime, can't send or receive data when down

## Bus Topology

Single connection = backbone cable, prone to slow if devices simultaneously request data, bottleneck troubleshoot to identify which device needs help, easier & more cost efficient, if cable breaks can't transmit data

## Ring Topology

Token topology connected directly to form a loop, devices will send own data first before sending another device's data, only one direction for data to travel, easy to troubleshoot, not efficient due to having to go through multiple devices to get to designated point

Less prone to bottleneck, cut cable will stop network

## Switch

Dedicated devices to aggregate networking cable devices using ethernet, found in businesses/schools, connect large number of devices using ports 4,8,16,24,32,64

More efficient than a hub/repeater because it keeps track of what device is connected to which port, when packet received, sends to intended target therefore reduces network traffic

Switches and routers can connect to one another allowing data to have multiple paths to take, may reduce performance but increases reliability

## Router

Connects network and pass data between them (routing), useful when devices connected by many paths

## Primer or Subnetting

Splitting up a network into miniature networks, networks need to know where to send information, system administrator categorizes and assign parts of a network

Splitting up hosts that can fit within a network, represented by a number called subnet mask, made up of 4 bytes (Ex. 192.168.1.1) (32 bits) (0-255)

Subnets utilize IP in 3 ways from identify network address, identify host address, identify default gateway

Network Address: Identifies start of actual network (192.168.1.0)

Host Address: Used to identify a device on the subnet (192.168.1.1)

Default Gateway: Special address assigned to device on network that is capable of sending information to another network (192.168.1.254)

At home one subnet vs businesses have multiple, benefits are efficiency, security, full control

## ARP

Address Resolution Protocol is technology responsible for allowing devices to identify themselves on a network, associate MAC address with IP address on a network, keep a log of MAC associated with other devices

Each device has a ledger to store information which is called a cache, cache stores identifiers of other devices on a network, to map MAC & IP together, ARP sends two types of messages in the form of ARP request and ARP reply

ARP request broadcast on network asking "What is MAC address that owns this IP address"

Other devices receiving will only respond if they own IP & will send ARP reply with it's MAC address

Requesting device now can remember and store it in it's ARP cache for future reference

## DHCP

IP addresses can be assigned manually or entered physically

Automatically by Dynamic Host Configuration Protocol server, when device connects to network, it sends out request DHCP discover to see if any DHCP servers are on

DHCP server will reply back with IP address device could use DHCP offer

Device sends a reply confirming offer of IP DHCP Request, DHCP acknowledging with reply, and device can start using IP DHCP ACK

## OSI Model

Open Systems Interconnection model essential in networking, framework of how network devices send, receive and interpret data

Benefits is that devices can have different functions and designs on network while communicating with other devices creating uniformed data to be understood sent across, Each layer has different responsibilities arranged from layer 7 to layer 1

Each layer data travels through specific processes take place and pieces of information are added to the data, process called encapsulation

Layer 1 (Physical): Physical components of hardware, electrical signals to transfer data between each other, binary numbering system (1s & 0s) (Ex. Ethernet Cable)

Layer 2 (Data Link): Data link layer focuses on physical addressing of transmission, It receives a packet from network layer includes IP & adds physical MAX of the receiving endpoint

Every network-enabled device has network interface card (NIC) comes with unique MAC to identify it

Responsible for presenting data in suitable format

Layer 3 (Network): Network layer is where routing & re-assembly of data takes place 

Small chunks to large where routing determines most optimal path for data to be sent

Open shortest path first (OSPF), Routing Information Protocol (RIP)

Factors like shortest path, most reliable, faster physical location, everything is dealt via IP, devices like routers capable of delivery packets using IP are known as layer 3 devices

Layer 4 (Transport): Transmitting data across network, data being sent between devices follow one of two different protocols based upon factors

Transmission Control Protocol (TCP), designed with reliability as protocol reserves constant connection between two devices for time it takes for data to be sent and received, error checking for small chunks in session layer 5 received and reassembled in same order

Advantages of TCP: Guarantee accuracy, synchronize two devices to prevent flooded data

Disadvantages of TCP: Requires reliable connection, if one chunk not received then entire chunk of data can't be used, significantly slower than UDP due to more work having to be done by devices

TCP used for situations like file sharing, internet browsing (services requiring accurate and complete)

User Datagram Protocol (UDP) not nearly as advances in sense does not error check, no synchronization between devices and more so hope for the best

Advantages of UDP: Much faster than TCP, application layer decides on how quickly packets sent, does not reserve continuous connection

Disadvantages of  UDP: Doesn't care if data is received, flexible to software developers, unstable connection results in terrible user experience

Useful when small pieces of data being sent like discovering devices (ARP/DHCP) or larger files like video streaming

Layer 5 (Session): Once data has been correctly translated/formatted from presentation layer, will begin to create/maintain connection to other computer which data is destined, when connection established = a session is created

While connection is active so is the session, responsible for closing the connection, can contain checkpoints in the case data is lost only newest pieces of data are required to be sent

Sessions are unique in the sense that data cannot travel over different sessions but across each session

Layer 6 (Presentation): Standardization takes place, data needs to be handled in same way no matte rhow software works, translator for data to and from application layer

Receiving computer will also understand data in one format, data encryption occurs at this layer (HTTPS)

Layer 7 (Application): Layer in which protocols and rules are in place to determine how user should interact with data sent or received, Graphical User Interface (GUI), (DNS) Domain Name System how websites addresses are translated into IP addresses

## Packets & Frames

Packets are small pieces of data when formed together create larger piece of information, Exchanged in small pieces for less chance of bottleneck

A frame is at layer 2 (data link layer) no such information as IP addresses

When talking about IP we are referring to packets, when encapsulation information stripped then we're talking about the frame itself

Internet protocol will have set of headers containing additional pieces of information

Time to leave: Sets expiry timer for packet to not clog network if it never reached host

Checksum: Integrity checking protocols of TCP/IP, corrupt 

Source Address: IP address of the device that sent packet so data knows where to return to

Destination Address: Address of packet being sent to so data knows where to travel next

Transmission Control Protocol (TCP)

Consist of four layers: Application, Transport, Internet, Network Interface

Summarized version of OSI model, information added to each layer as packets traverses it (encapsulation), and reverse process is decapsulation

Defining feature is connection-based, must establish connection between client and device before data sent, process known as Three-way handshake

Advantages of TCP: Guarantee integrity of data, a lot more processes for reliability

Disadvantages of TCP: Requires a reliable connection, slow connection can bottleneck, slower than UDP

## Headers 

Source Port: Port opened by sender to send TCP packet (0-65535), random value chosen

Destination Port: Port number for receiving data, this value is not random

Source IP: IP address of device sending packet

Destination IP: IP address of device packet destined for

Sequence number: Connection occurs, first piece of data is given random number

Acknowledgement number: after first piece given a sequence number, next piece will have sequence + 1

Checksum: The value of mathematical calculation to remember output sent

Data: Bytes of a file is transmitted stored in header

Flag: Determines how packet should be handled

## Three-way handshake Messages

SYN (1): Initial packet sent by client to initiate connection

SYN/ACK (2): Packet send by receiving device to acknowledge synchronization attempt

ACK (3): Acknowledgment packet used to notify successfully received

DATA (4): Data (bytes if files) sent via DATA message

FIN (5): Packet used to cleanly close connection after it has been complete

RST (6): Abruptly ends all communication , last resort when problem occurs

Any sent data is given random number sequence agreed upon by both devices to be sent in correct order

	1) SYN- Client: initial (ISN) initial sequence number to SYNchronize with (0)
	2) SYN/ACK- Server: initial (ISN) to SYNchronize with (5000) and I ACKnowledge your nintial number sequence (0)
	3) ACK- Client: ACKnowledge your ISN of (5000), here is some data that is my ISN+1 (0+1)

TCP will close a connection once other device has successfully received all data, reserves system resources when on a device, device will send a "FIN" packet to other device to initiate closure

## UDP/IP

User Diagram Protocol another protocol to communicate data between devices, stateless that doesn't require constant connection between two devices for data to be sent (no synchronization needed)

Advantages of UDP: much faster than TCP, control how quick packets are sent, doesn't reserve continuous connection

Disadvantages of UDP: doesn't care if data is received, flexible to developers, unstable connection results in terrible user experience

Header

Time to Live (TTL): expiry timer for packet that didn't reach host

Source Address: IP address of packet being sent from

Destination Address: IP address the packet is being sent to

Source Port: port that is opened by sender, randomly chosen

Destination Port: port number that application is running on, value not chosen random

Data: header is where data/bytes of file is being transmitted/stored

No acknowledgment is sent during connection (use for video calls)

## Ports 101 (practical)

Ports are essential in which data can be exchanged, enforce what can park and where, strict rules where data sent or received are sent through these ports, (65,535) (0-6535)

Associate applications and software with standard set of rules to not lose track of what application is using what port, web browsers use port 80

Any port that is 0-1024 (1,024) is known as common port

File Transfer Protocol (FTP): Port 21: file-sharing application, download files from central location

Secure Shell (SSH): Port 22: Securely login to systems via text-based interface

HyperText Transfer Protocol (HTTP): Port 80: powers the (WWW), browser uses this to download text/videos

HyperText Transfer Protocol Secure (HTTPS): Port 443: Does same exact as above but securely using encryption

Server Message Block (SMB):  Port 445: Similar to (FTP) but as well as files, SMB allows to share devices like printers

Remove Desktop Protocol (RDP): Port 3389: Secure means of logging in a system using visual desktop interface opposed to limitations of SSH protocol

You can administer applications outside of standard like web server doesn't have to do port 80, however have to provide colon (:) along with port number

## Introduction to Port Forwarding

Connecting applications and services to the internet, without port forwarding applications and services like web servers are only available to devices on direct network, configured at the router of a network

Intranet is server with same IP can only be accessed by computers on that network

Port forwarding opens specific ports while firewalls determine if traffic can travel across ports even if ports are open by port forwarding

## Firewalls 101

Device within a network responsible for determining traffic allowed to enter & exit,  administrator can configure firewall to permit or deny traffic

Where is the traffic is coming from, where is the traffic going, what port is the traffic for, and what protocol is the traffic using

Packet inspection to answer those questions above, firewalls come in all shapes/sizes

Dedicated hardware pieces (businesses) handle magnitude of data, to residential routers for your home, software such as Snort, firewalls categorized into 2-5 categories

Two primary categories 

Stateful: This type of firewall uses entire information from connection, instead of inspecting packets, determines behavior of device based upon entire connection, consumes a lot of resources resulting in dynamic decision making (allowing first part of TCP then fail later) (block if connection from host bad)

Stateless: This firewall type uses static set of rules to determine whether individual packets are acceptable or not, if device sends bad packet then entire device won't be blocked, use much fewer resources but much dumber (only effective depending on rules that define them) (great at receiving large amounts of traffic from host DDOS)

## VPN Basics
