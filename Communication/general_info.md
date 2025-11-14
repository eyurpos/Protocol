# OSI model

## General

| Data Unit | Layer        | Purpose                              | Protocols | TCP/IP      |
|-----------|--------------|--------------------------------------|-----------|-------------|
| Data      | Application  | Helps in identifying the client      | HTTP,     |             |
|           |              | and synchronizing communication.     | FTP       |             |
|           |              | Data from the application layer is   | SSL,      |             |
| Data      | Presentation | extracted and manipulated in the     | TSL       | Application |
|           |              |required format for transmission.     |           |             |
| Data      | Session      | Establishes Connection, Maintenance, | RPC,      |             |
|           |              | Ensures Authentication and security. | PPTP      |             |
| Segments  | Transport    | Take Service from Network Layer and  | TCP,      | Transport   |
|           |              | provide it to the Application Layer. | UDP       |             |
|           |              | Transmission of data from one host   | IP        |             |
| Packets   | Network      | to another, located in different     |           | Internet    |
|           |              | networks.                            |           |             |
| Frames    | Link         | Node to Node Delivery of Message.    | ARP, MAC, |             |
|           |              |                                      | Ethernet  | Network     |
| Bits      | Physical     | Establishing Physical Connections    | USB,      | Acces       |
|           |              | between Devices.                     | Etherntet |             |


https://www.geeksforgeeks.org/computer-networks/open-systems-interconnection-model-osi/

> ifconfig -a

> ip addr show - device name, MAC, subnet mask

## 1. Physical layer
The lowest layer of the OSI reference model is the Physical Layer. It is responsible for the actual physical connection between the devices. The physical layer contains information in the form of bits. Physical Layer is responsible for transmitting individual bits from one node to the next. When receiving data, this layer will get the signal received and convert it into 0s and 1s and send them to the Data Link layer, which will put the frame back together.

> ip link set dev <name> up

> ip link set dev <name> down

## 2. Data Link Layer 
The data link layer is responsible for the node-to-node delivery of the message. The main function of this layer is to make sure data transfer is error-free from one node to another, over the physical layer. When a packet arrives in a network, it is the responsibility of the DLL to transmit it to the Host using its MAC address. Packet in the Data Link layer is referred to as Frame.

### Ethernet II Frame Format

| Preamble |   SFD  |  DMAC    |    SMAC    |    Type     |        Data        |   CRC    |
|----------|--------|----------|------------|-------------|--------------------|----------|
| 7 Bytes  | 1 Byte | 6 Bytes  |   6 Bytes  |   2 Bytes   |  Variable length   | 4 Bytes  |

https://www.geeksforgeeks.org/computer-networks/ethernet-frame-format/

### ARP
The acronym ARP stands for Address Resolution Protocol which is one of the most important protocols of the Data link layer in the OSI model. 

https://www.geeksforgeeks.org/ethical-hacking/how-address-resolution-protocol-arp-works/

> arp -a

## 3. Network Layer
The network layer works for the transmission of data from one host to the other located in different networks. It also takes care of packet routing i.e. selection of the shortest path to transmit the packet, from the number of routes available. The sender and receiver's IP address are placed in the header by the network layer. Segment in the Network layer is referred to as Packet. 

A default gateway is the node in a computer network using the Internet protocol suite that serves as the forwarding host (router) to other networks when no other route specification matches the destination IP address of a packet.

### IP
https://www.geeksforgeeks.org/computer-networks/what-is-internet-protocol-ip/

#### Private (Local) IP Address Ranges: 
- 10.0.0.0 - 10.255.255.255: (often used in larger networks)
- 172.16.0.0 - 172.31.255.255: (often used in larger networks)
- 192.168.0.0 - 192.168.255.255: (commonly used in home networks)
- 100.64.0.0 - 100.127.255.255: (for Carrier-Grade NAT)

#### Public (Global) IP Address Ranges: 
- 1.0.0.0 - 9.255.255.255
- 11.0.0.0 - 126.255.255.255
- 129.0.0.0 - 169.253.255.255
- 169.255.0.0 - 172.15.255.255
- 172.32.0.0 - 191.0.1.255
- 192.0.3.0 - 192.88.98.255
- 192.88.100.0 - 192.167.255.255
- 192.169.0.0 - 198.17.255.255
- 198.20.0.0 - 223.255.255.255 

### DHCP
Dynamic Host Configuration Protocol is a network protocol used to automate the process of assigning IP addresses and other network configuration parameters to devices (such as computers, smartphones and printers) on a network.
https://www.geeksforgeeks.org/computer-networks/dynamic-host-configuration-protocol-dhcp/

> sudo ip addr add AAA.BBB.CCC.DDD/MASK dev [name]

> sudo ip addr del AAA.BBB.CCC.DDD/MASK dev [name]

> ip addr flush dev [name] - del all ip


> ip route show

> ip route get [ip]

> sudo ip -6 route add/del default via {gateway_ipv6_address} dev {network_interface_name}


> ping

> traceroute

## 4. Transport Layer
The transport layer provides services to the application layer and takes services from the network layer. The data in the transport layer is referred to as Segments. It is responsible for the end-to-end delivery of the complete message. The transport layer also provides the acknowledgment of the successful data transmission and re-transmits the data if an error is found.

### TCP
TCP connections are established through a three-way handshake (SYN, SYN-ACK, ACK) and terminated by a four-way handshake (FIN, ACK, FIN, ACK) or a one-sided termination. 

1. Connection Establishment (Three-Way Handshake):
The client sends a SYN (synchronize) packet to the server. 
The server responds with a SYN-ACK (synchronize-acknowledge) packet, also including its own sequence number. 
The client then sends an ACK (acknowledge) packet to the server, completing the handshake and establishing the connection. 
2. Data Transfer:
TCP breaks data into segments and adds a header containing sequence numbers, acknowledgment numbers, and other control information. 
The sequence numbers ensure that the data is reassembled in the correct order on the receiving end. 
The acknowledgment numbers confirm that segments have been received. 
3. Flow Control:
TCP uses a sliding window mechanism to regulate the flow of data. 
The receiver advertises its window size, indicating how much data it can receive at a time. 
The sender adjusts its sending rate based on the advertised window size, preventing buffer overflows and congestion. 
4. Connection Termination (Four-Way Handshake or One-Sided):
Either the client or server can initiate the termination process. 
It involves sending a FIN (finish) packet, followed by an ACK, and then the other side sends a FIN, followed by an ACK. 
One-sided termination is also possible, where one side closes its connection while the other side continues sending data. 

https://www.ionos.com/digitalguide/server/know-how/introduction-to-tcp/


### Port
A port is a virtual point where network connections start and end. Ports are software-based and managed by a computer's operating system. Each port is associated with a specific process or service. Ports allow computers to easily differentiate between different kinds of traffic: emails go to a different port than webpages, for instance, even though both reach a computer over the same Internet connection.

https://www.geeksforgeeks.org/computer-networks/what-is-ports-in-networking/

- Port 20/21: File Transfer Protocol (FTP) – Used for transferring files between clients and servers.
- Port 22: Secure Shell (SSH) – Enables a secure remote connection to systems for administration and file transfer.
- Port 23: Telnet – An older, unsecure protocol for remote access to computers (now mostly replaced by SSH).
- Port 25: Simple Mail Transfer Protocol (SMTP) – Used for sending emails between mail servers.
- Port 53: Domain Name System (DNS) – Translates domain names into IP addresses and vice versa.
- Port 80: Hypertext Transfer Protocol (HTTP) – Standard port for unencrypted websites.
- Port 110: Post Office Protocol (POP3) – Used by email clients to retrieve emails from a server.
- Port 123: Network Time Protocol (NTP) – Used for time synchronization between computers in a network.
- Port 143: Internet Message Access Protocol (IMAP) – A more modern protocol than POP3 for accessing emails.
- Port 161: Simple Network Management Protocol (SNMP) – Used to monitor and manage network devices.
- Port 443: HTTP Secure (HTTPS) – For encrypted web communication, especially important for secure transactions.

### NAT
Network Address Translation allows (NAT) multiple devices to use the same public IP address and access the Internet.

https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/


## 5. Session Layer
The Session Layer is the 5th layer in the Open System Interconnection (OSI) model which plays an important role in controlling the dialogues (connections) between computers. This layer is responsible for setting up, coordinating, and terminating conversations, exchanges, and dialogues between the applications at each end. It establishes, manages, and terminates the connections between the local and remote applications.

## 6. Presentation Layer 
Presentation Layer is the 6th layer in the Open System Interconnection (OSI) model. This layer is also known as Translation layer, as this layer serves as a data translator for the network. The data which this layer receives from the Application Layer is extracted and manipulated here as per the required format to transmit over the network.

## 7. The Application Layer 
The Application Layer of OSI (Open System Interconnection) model, is the top layer in this model and takes care of network communication. The application layer provides the functionality to send and receive data from users. It acts as the interface between the user and the application. The application provides services like file transmission, mail service, and many more.

## Domain Name System (DNS)
DNS is a hierarchical and distributed naming system that translates domain names into IP addresses.

- User Input: You enter a website address (for example, www.geeksforgeeks.org) into your web browser.
- Local Cache Check: Your browser first checks its local cache to see if it has recently looked up the domain. If it finds the corresponding IP address, it uses that directly without querying external servers.
- DNS Resolver Query: If the IP address isn’t in the local cache, your computer sends a request to a DNS resolver. The resolver is typically provided by your Internet Service Provider (ISP) or your network settings.
- Root DNS Server: The resolver sends the request to a root DNS server. The root server doesn’t know the exact IP address for www.geeksforgeeks.org but knows which Top-Level Domain (TLD) server to query based on the domain’s extension (e.g., .org).
- TLD Server: The TLD server for .org directs the resolver to the authoritative DNS server for geeksforgeeks.org.
- Authoritative DNS Server: This server holds the actual DNS records for geeksforgeeks.org, including the IP address of the website’s server. It sends this IP address back to the resolver.
- Final Response: The DNS resolver sends the IP address to your computer, allowing it to connect to the website’s server and load the page

* Root DNS Servers: These are the highest-level DNS servers and know where to find the TLD servers. They are crucial for directing DNS queries to the correct locations.
* TLD Servers: These servers manage domain extensions like .com, .org, .net, .edu, .gov and others. They help route queries to the authoritative DNS servers for specific domains.
* Authoritative DNS Servers: These are the servers that store the actual DNS records for domain names. They are responsible for providing the correct IP addresses that allow users to reach websites.

https://www.geeksforgeeks.org/computer-networks/domain-name-system-dns-in-application-layer/

> host -a google.com

> dig @a.root-servers.net com NS

> dig @e.gtld-servers.net google.com NS

> dig @ns1.google.com google.com any

> nano /etc/hosts - manual domain i mapping

> sudo resolvectl statistics

> sudo resolvectl status 

> sudo resolvectl flush-caches - flush DNS cash

## Wireshark

https://www.geeksforgeeks.org/linux-unix/how-to-install-and-use-wireshark-on-ubuntu-linux/

https://www.wireshark.org/docs/wsug_html_chunked/ChCustCommandLine.html