Module 5: Networking
Lesson 1: Networking concepts
1. OSI models
Went over OSI model layers again. The model describes how communications should occur in a computer network.
1= Physical. Deals with physical connection between devices. Electrica, optical, wireless signals.
2= Data link. Describes an agreement between the different systems on the same network segment on how to communicate. Etehrnet, WiFi
3= Network. Logical addressing and routing between networks. IP, ICMP, IPSec
4= Transport. End-to-end communication and data segmentation. UDP, TCP
5= Session. Establishing, maintaining, and synchronising sessions. NFC, RPC
6= Presentation. Data encoding, encryption, and compression. Unicode, MIME, JPEG, PNG, MPEG
7= Application. Providing services and interfaces to applications. HTTP, FTP, DNS, POP3, SMTP, IMAP.

2. IP Addresses and Subnets
- IP is a a unique identifier for the host, and host cannot be found without an IP address.
- An IP address comprises four octets, i.e., 32 bits. Being 8 bits, an octet allows us to represent a decimal number between 0 and 255.
- Example: 192.168.1.0 is the network address, and 192.168.1.255 is the broadcast address.
- To look up your IP address in the MS Windows: "ipconfig". For Linux and UNIX-based systems: "ifconfig", or "ip a s". 
- Private IP address is an address that cannot reach or be reached from outside. To access the Internet, a private address must have a router that has a public IP address and must support Network Address Translation.
- A router is a device that routes data packets to a proper network. Functions at level 3 of the OSI model.

3. UDP and TCP
Both are protocols that enable processes on network hosts to communicate with eachother.
More about this topic in Day 7: UDP and TCP.

4. Telnet
TELNET (Teletype Network) protocol is a network protocol for remote terminal connection.
To connect to a target VM we can use "telnet MACHINE IP 7" where 7 is the port that we connect to.
To identify the host where any information goes we can issue a command "GET / HTTP/1.1" (we have to be connected to port 80, as HTTP usually runs on that port) 

Practical:
I connected to the VM web server using telnet, and discovered that it runs on the version lighttpd/1.4.63.
I viewed the host page using GET / HTTP/1.1 and captured the flag.

