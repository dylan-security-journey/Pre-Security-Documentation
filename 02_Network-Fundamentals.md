# Networking Fundamentals

---

## 1. What is Networking?
- **Networking** = Devices connected together.  
- Forms the backbone of both **private** (local) and **public** (internet) communications.

---

## 2. Internet
- **Tim Berners-Lee** → Invented the **World Wide Web (WWW)**.  
- Internet = collection of **small networks** connected together.  
  - **Private Networks** → Local, internal.  
  - **Public Networks** → Connect small networks globally.  

---

## 3. Identifying Devices
- Devices are identified with two addresses:  
  1. **IP Address** → Logical address.  
     - IPv4: 4 octets (0–255), e.g., `192.168.1.1`.  
     - Public IP → given by **ISP** (Internet Service Provider).  
     - Private IP → used internally on local networks.  
  2. **MAC Address** → Hardware serial number (12 hex digits).  
     - First 6 digits = manufacturer.  
     - Last 6 digits = unique device identifier.  
     - **MAC Spoofing** → Pretending to be another device.  

---

## 4. IPv6 vs IPv4
- **IPv4** → `2^32` addresses (~4.29B). Example: `86.157.52.21`.  
- **IPv6** → `2^128` addresses (~340 trillion trillion). Example: `2a00:22C4:a531:c500`.  
- Needed because IPv4 addresses are running out.  

---

## 5. Ping (ICMP)
- **Ping** uses **ICMP (Internet Control Message Protocol)**.  
- Tests connectivity by sending an **echo request** and receiving an **echo reply**.  
- Measures round-trip latency.  

---

## 6. Network Topologies

### Star Topology
- Devices connected to a central hub/switch.  
- **Pros**: Scalable, easy to add devices.  
- **Cons**: More expensive, downtime if central device fails.  

### Bus Topology
- Devices share a single backbone cable.  
- **Pros**: Simple, cheap.  
- **Cons**: Bottlenecks, if cable breaks → entire network fails.  

### Ring Topology
- Devices connected in a loop (token passing).  
- **Pros**: Easy troubleshooting, fewer bottlenecks.  
- **Cons**: Inefficient, if one cable/device fails → network stops.  

---

## 7. Networking Devices

### Switch
- Aggregates multiple devices via **Ethernet ports** (4–64).  
- Tracks MAC addresses → sends packets only to target device.  
- More efficient than a hub/repeater.  
- Switches + routers can connect for redundancy.

### Router
- Connects different networks, passes data between them (**Layer 3**).  
- Chooses paths based on reliability, shortest route, or speed.  
- Can include firewalling, port forwarding, and DHCP features.

---

## 8. Subnetting
- Dividing a network into **smaller sub-networks**.  
- Uses **Subnet Mask** (4 bytes, 32 bits). Example: `192.168.1.0/24`.  
- Types of addresses:  
  - **Network Address** → Start of network (e.g., `192.168.1.0`).  
  - **Host Address** → Device within subnet (e.g., `192.168.1.1`).  
  - **Default Gateway** → Device that routes outside (e.g., `192.168.1.254`).  
- **Benefits**: Efficiency, security, control.  

---

## 9. ARP (Address Resolution Protocol)
- Maps **IP addresses ↔ MAC addresses**.  
- Maintains a **cache** of device mappings.  
- Uses two messages:  
  - **ARP Request**: “Who owns this IP?” (broadcast).  
  - **ARP Reply**: Device responds with its MAC address.  

---

## 10. DHCP (Dynamic Host Configuration Protocol)
- Automates IP address assignment.  
- Process:  
  1. **Discover** → Client looks for DHCP server.  
  2. **Offer** → Server offers an IP.  
  3. **Request** → Client requests the offered IP.  
  4. **ACK** → Server confirms assignment.  

---

## 11. OSI Model (7 Layers)
Framework for how devices send, receive, and interpret data.  

1. **Physical** → Cables, signals, binary.  
2. **Data Link** → MAC addressing, NIC cards.  
3. **Network** → Routing, IP addressing (Routers, OSPF, RIP).  
4. **Transport** → TCP (reliable, slow) vs UDP (fast, no guarantees).  
5. **Session** → Establishes and maintains connections.  
6. **Presentation** → Data formatting, encryption (HTTPS).  
7. **Application** → User-facing protocols (DNS, HTTP, FTP).  

- **Encapsulation** → Each layer adds headers to data.  
- **TCP vs UDP**:  
  - TCP → Reliable, ordered, slower. (e.g., browsing, file transfer).  
  - UDP → Fast, unreliable. (e.g., video streaming, ARP, DHCP).  

---

## 12. Packets & Frames
- **Packet** = Data at the **network layer (IP)**.  
- **Frame** = Data at the **data link layer (MAC)**.  
- **Headers** add metadata:  
  - TTL → Time-to-live expiration.  
  - Checksum → Error detection.  
  - Source/Destination IP & Port.  

---

## 13. TCP – Three-Way Handshake
1. **SYN** → Client requests connection.  
2. **SYN/ACK** → Server acknowledges.  
3. **ACK** → Client confirms.  
4. **DATA** → Transmission begins.  
5. **FIN** → Graceful closure.  
6. **RST** → Abrupt termination.  

- Ensures reliability and synchronization.  

---

## 14. UDP/IP
- **UDP** = Connectionless, no acknowledgment.  
- **Pros**: Fast, flexible.  
- **Cons**: Unreliable, may drop data.  
- Used in **video calls, streaming, discovery protocols**.  

---

## 15. Ports 101
- **65,535 total ports** (0–65535).  
- **0–1024 = Well-known ports**.  

| Protocol | Port | Purpose |
|----------|------|---------|
| FTP      | 21   | File Transfer |
| SSH      | 22   | Secure remote login |
| HTTP     | 80   | Web traffic |
| HTTPS    | 443  | Secure web traffic |
| SMB      | 445  | File + device sharing |
| RDP      | 3389 | Remote Desktop |

---

## 16. Port Forwarding
- Opens specific ports on a router → allows external devices to access services inside a network.  
- Works with **firewalls** to control traffic.  
- Example: Hosting a web server at home.  

---

## 17. Firewalls
- Control **inbound & outbound traffic**.  
- Decide based on source, destination, port, and protocol.  

### Types
- **Stateless Firewall** → Uses fixed rules, lightweight.  
- **Stateful Firewall** → Monitors full connections, resource-heavy but smarter.  

---

## 18. VPN Basics
- **VPN (Virtual Private Network)** = Encrypted “tunnel” across the internet.  
- Benefits:  
  - Connects remote offices.  
  - Privacy (encrypted traffic).  
  - Anonymity (hides traffic from ISP).  
- Protocols:  
  - **PPP/PPTP** → Old, weak encryption.  
  - **IPSec** → Strong encryption, more complex.  

---

## 19. LAN Networking Devices

### Router
- Connects networks, determines best path for data.  
- Operates at **Layer 3**.  
- Can manage port forwarding, firewalling, and routing rules.  

### Switch
- Connects multiple devices in a LAN.  
- Operates at **Layer 2** (MAC addressing).  
- Layer 3 switches = can route like routers.  
- **VLANs** → Logically split networks for security and control.  

---

## Key Takeaways
- **IP + MAC** uniquely identify devices.  
- **IPv6** solves IPv4 exhaustion.  
- **Ping, ARP, DHCP** are fundamental protocols.  
- **OSI vs TCP/IP** → Different models, same goal: standardization.  
- **TCP = reliable** vs **UDP = fast**.  
- **Ports, firewalls, and VPNs** are critical for securing communication.  
