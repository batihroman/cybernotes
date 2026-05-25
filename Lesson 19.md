Module 5: Networking
Lesson 19: Networking Essentials

1. The Dynamic Host Configuration Protocol (DHCP).
It follows four steps:
- DHCP Discover: The client broadcasts a DHCPDISCOVER message seeking the local DHCP server if one exists.
- DHCP Offer: The server responds with a DHCPOFFER message with an IP address available for the client to accept.
- DHCP Request: The client responds with a DHCPREQUEST message to indicate that it has accepted the offered IP.
- DHCP Acknowledge: The server responds with a DHCPACK message to confirm that the offered IP address is now assigned to this client.

- Client always starts without any IP network configuration, only MAC address. In the first and third packet it sends packets from IP 0.0.0.0 to the broadcast IP address 255.255.255.255.
- For the link layer, in 1st and 3rd packets, client sends to the broadcast MAC address ff:ff:ff:ff:ff:ff, the DHCP offers available IP address along with network configuration in the offer.

2. ARP: Layer 3 Addressing to Layer 2 Addressing
Address Resolution Protocol (ARP) makes it possible to find the MAC address of another device on the Ethernet.
- A host wants to communicate with another device on the network and sends an Arp request asking the host with a certain IP address to respond.
- The ARP Request is sent from the MAC address of the requester to the broadcast MAC address, ff:ff:ff:ff:ff:ff.
- It gets the ARP reply and the host with a wanted IP address responds with it's MAC address. Now they can exchange data link layer frames.

3. ICMP
Internet Control Message Protocol (ICMP) is mainly used for network diagnostics and error reporting.
Two commands that rely on ICMP are: 
- "ping" to test connectivity to a target system and measures the round-trip time. It sends an Echo Request (ICMP type 8). The computer on the receiving end responds with an ICMP Echo Reply (ICMP Type 0). You can also use "-c NUMBER" to tell the ping command to stop after sending wanted number of requests.
- "traceroute" on Linux, but "tracert" on MS Windows. It uses ICMP to discover the route from your host to the target. When the TTL reaches zero, the router drops the packet and sends an ICMP Time Exceeded message (ICMP Type 11).

4. Routing
Routing algorithms:
- OSPF (Open Shortest Path First): OSPF is a routing protocol that allows routers to share information about the network topology and calculate the most efficient paths for data transmission. It does this by having routers exchange updates about the state of their connected links and networks.
- EIGRP (Enhanced Interior Gateway Routing Protocol): EIGRP is a Cisco proprietary routing protocol that combines aspects of different routing algorithms. It allows routers to share information about the networks they can reach and the cost associated with those routes.
- BGP (Border Gateway Protocol): BGP is the primary routing protocol used on the Internet. It allows different networks to exchange routing information and establish paths for data to travel between these networks.
- RIP (Routing Information Protocol): RIP is a simple routing protocol often used in small networks. Routers running RIP share information about the networks they can reach and the number of hops (routers) required to get there. 

5. Network Address Translation (NAT)
With NAT using one public IP address you can provide Internet access to many private IP addresses on the network.

