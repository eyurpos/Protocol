# User Datagram Protocol - UDP

https://www.geeksforgeeks.org/computer-networks/user-datagram-protocol-udp/

User Datagram Protocol (UDP) is a Transport Layer protocol of the Internet Protocol (IP) that provides fast, connectionless, and lightweight communication between processes. It does not guarantee delivery, order, or error checking, making it suitable for real-time and time-sensitive applications such as video streaming, DNS, and VoIP.

![0](./images/UDP-gif.gif)




User Datagram Protocol - UDP
Last Updated : 14 Oct, 2025
User Datagram Protocol (UDP) is a Transport Layer protocol of the Internet Protocol (IP) that provides fast, connectionless, and lightweight communication between processes. It does not guarantee delivery, order, or error checking, making it suitable for real-time and time-sensitive applications such as video streaming, DNS, and VoIP.

UDP

UDP Header
UDP header is 8 bytes long, followed by the data payload. It contains all the essential information needed for transmission. Each port number field is 16 bits, giving a range from 0 to 65535, where port 0 is reserved. Port numbers are used to identify and separate different user requests or processes.

UDP-header
UDP Header
Field	Size	Description
Source Port	16 bits	Identifies the sender’s port number.
Destination Port	16 bits	Identifies the receiver’s port number.
Length	16 bits	Specifies the total length of UDP header and data.
Checksum	16 bits	Used for error detection (optional in IPv4, mandatory in IPv6).
Notes: Unlike TCP, checksum in UDP is optional, it provides no error or flow control, relying on IP/ICMP for error reporting, while port numbers help differentiate user requests.

# Applications of UDP
UDP is preferred where low latency is crucial and occasional packet loss is acceptable:

- DNS uses UDP for fast query/response lookups since domain name queries are small and need quick replies.
- DHCP uses UDP to dynamically assign IP addresses to devices, where small control messages are exchanged.
- VoIP uses UDP for real-time voice communication, as it tolerates some packet loss but not delays.
- RIP uses UDP to send periodic routing updates between routers efficiently.
- NTP uses UDP to synchronize system clocks across networks with minimal overhead.