# What is Ports in Networking?
https://www.geeksforgeeks.org/computer-networks/what-is-ports-in-networking/

Whenever any application in one computer sends data to another application of a different computer then it sends using IP Address and MAC Address but how does our computer know that this data is for a specific application and this data is sent by any specific application? There comes the concept of Port.

Now every time any application sends any data, it is identified by the port that which the application sent that data and the data is to be transferred to the receiver application according to its port. We often call port as port number.

In the OSI Model ports are used in the Transport layer. In the headers of Transport layer protocols like TCP and UDP, we have a section to define port(port number). The network layer has to do nothing with ports, their protocols only care about IP Addresses.

Ports are assigned by computer i.e. operating system to different applications. Ports help computer to differentiate between incoming and outgoing traffic. Since the port is a 16-bit unsigned number it ranges from 0 to 65535.

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