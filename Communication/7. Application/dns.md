# Domain Name System (DNS)

https://www.geeksforgeeks.org/computer-networks/domain-name-system-dns-in-application-layer/

DNS is a hierarchical and distributed naming system that translates domain names into IP addresses. When you type a domain name like www.geeksforgeeks.org into your browser, DNS ensures that the request reaches the correct server by resolving the domain to its corresponding IP address.

## Working of DNS

![1](./images/frame_5.webp)
![2](./images/dns_resolver_step3.webp)
![3](./images/step_3.webp)
![4](./images/step_4.webp)
![5](./images/dns_resolver_step4.webp)

## Structure of DNS
DNS operates through a hierarchical structure, ensuring scalability and reliability across the global internet infrastructure. Here's how it’s organized:

- Root DNS Servers: These are the highest-level DNS servers and know where to find the TLD servers. They are crucial for directing DNS queries to the correct locations.
- TLD Servers: These servers manage domain extensions like .com, .org, .net, .edu, .gov and others. They help route queries to the authoritative DNS servers for specific domains.
- Authoritative DNS Servers: These are the servers that store the actual DNS records for domain names. They are responsible for providing the correct IP addresses that allow users to reach websites.

![6](./images/root_dns_server.webp)

## Types of Domains
DNS helps manage a wide variety of domain types to organize the vast number of websites on the internet. Here are the primary categories:

- Generic Domains: These include top-level domains like .com, .org, .net and .edu. These are widely used and recognized across the world.
- Country Code Domains: These domains represent specific countries or regions, such as .in for India, .us for the United States, .uk for the United Kingdom and .jp for Japan.
- Inverse Domains: Used for reverse DNS lookups, these domains help map IP addresses back to domain names. Reverse DNS lookups are useful for diagnostics and security purposes, ensuring that the source of network traffic is legitimate. So DNS can provide both the mapping for example to find the IP addresses of geeksforgeeks.org then we have to type

![7](./images/root.webp)

# Domain Name Server
The client machine sends a request to the local name server, which, if the root does not find the address in its database, sends a request to the root name server, which in turn, will route the query to a top-level domain (TLD) or authoritative name server.

- The root name server can also contain some hostName to IP address mappings.
- The Top-level domain (TLD) server always knows who the authoritative name server is.
- So finally the IP address is returned to the local name server which in turn returns the IP address to the host

## DNS Caching and TTL (Time-to-Live)
- DNS caching is a mechanism that stores DNS records locally to avoid querying external DNS servers repeatedly for the same information. This speeds up the browsing experience and reduces network traffic.
- TTL (Time-to-Live) is the amount of time that a DNS record is cached before it expires. When the TTL expires, the cache is cleared and a fresh DNS query must be made. The TTL is defined by the authoritative DNS server, which can adjust this based on the nature of the domain.