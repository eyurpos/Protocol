# NAT

https://www.geeksforgeeks.org/computer-networks/network-address-translation-nat/

Network Address Translation (NAT) is a networking technique that allows multiple devices within a private network to access external networks (like the Internet) using a single public IP address. By translating private IP addresses into public IP addresses and vice versa, NAT conserves the limited pool of IPv4 addresses and adds a layer of security by masking internal addresses from the outside world.

![0](./images/7.jpg)

## Working of NAT
When a device within a private network wants to communicate with the Internet, the request first goes to the NAT - enabled router. The router replaces the private IP address with its public IP address and assigns a unique port number. This mapping is recorded in the NAT table.

![1](./images/working_of_nat.webp)

This mechanism ensures:
- Multiple devices can share a single public IP.
- Internal addresses remain hidden from external networks.
- Port numbers help differentiate traffic from different devices.