# Transmission Control Protocol - TCP

https://www.geeksforgeeks.org/computer-networks/what-is-transmission-control-protocol-tcp/

Transmission Control Protocol (TCP) is a connection-oriented protocol for communications that helps in the exchange of messages between different devices over a network. It is one of the main protocols of the TCP/IP suite. In OSI model, it operates at the transport layer(Layer 4). It lies between the Application and Network Layers which are used in providing reliable delivery services. The Internet Protocol (IP), which establishes the technique for sending data packets between computers, works with TCP.

![0](./images/TCP-Gif.gif)

- TCP establishes a reliable connection between sender and receiver using the three-way handshake (SYN, SYN-ACK, ACK) and it uses a four-step handshake (FIN, ACK, FIN, ACK) to close connections properly.
- It ensures error-free, in-order delivery of data packets.
- It uses acknowledgments (ACKs) to confirm receipt.
- It prevents data overflow by adjusting the data transmission rate according to the receiver’s buffer size.
- It prevents network congestion using algorithms like Slow Start, Congestion Avoidance, Fast Retransmit, and Fast Recovery.
- TCP header uses checksum to detect corrupted data and requests retransmission if needed.
- It is used in applications requiring reliable and ordered data transfer, such as web browsing, email, and remote login.

## Features of TCP
Some of the most prominent features of Transmission control protocol are mentioned below.

- Segment Numbering: Each byte of data is numbered, and segments carry sequence numbers. Acknowledgment numbers confirm successful receipt.
- Connection-Oriented: Sender and receiver remain connected until data transfer is complete. Data order is preserved.
- Full Duplex: Data can flow in both directions simultaneously, improving efficiency.
- Flow Control: Uses a sliding window to prevent the sender from overwhelming the receiver.
- Error Control: Detects and manages corrupted, lost, duplicate, or out-of-order segments to ensure reliability.
- Congestion Control: Adjusts the sending rate based on network congestion to avoid overload.

## Advantages of TCP
- It is a reliable protocol which provides an error-checking mechanism as well as one for recovery.
- It makes sure that the data reaches the proper destination in the exact order that it was sent.
- It is a well-documented and widely implemented protocol, maintained by standards organizations like the IETF (Internet Engineering Task Force).
- It works in conjunction with IP (Internet Protocol) to establish connections between devices on a network.

## Disadvantages of TCP
- TCP is made for Wide Area Networks, thus its size can become an issue for small networks with low resources.
- TCP runs several layers so it can slow down the speed of the network.
- It is not generic in nature. It cannot represent any protocol stack other than the TCP/IP suite. E.g., it cannot work with a Bluetooth connection.
- No modifications since their development around 30 years ago.