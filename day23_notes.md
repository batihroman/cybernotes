Section 5: Networking
Lesson 23: TCPdump Basics

Commands and scenarios learned for tcpdump:
- ip a s:  list the available network interfaces
- -w FILE: to save the file
- -r FILE: to read the saved file
- -c COUNT: specify the number of packets to capture by specifying the count
- -nn: to stop both DNS and port number from resolving from e.g: port 80>hhtp
- -v: will print “the time to live, identification, total length and options in an IP packet
- -vv: will produce more verbose output
- -vvv:  will provide even more verbosity
- Example of the command (might require the password): sudo tcpdump -i ens5 -c 5 -n
- greater LENGHT: Filters packets that have a length greater than or equal to the specified length
- less LENGHT: Filters packets that have a length less than or equal to the specified length
- `q`: Quick output; print brief packet information
- `e`: Print the link-level header
- `A`: Show packet data in ASCII
- `xx`: Show packet data in hexadecimal format, referred to as hex
- `X`: Show packet headers and data in hex and ASCII
- `tcpdump -i wlo1 -w data.pcap` captures packets by listening on the `wlo1` interface (the WiFi interface) and writes the packets to `data.pcap`.
- `tcpdump -i any -nn` captures packets on all interfaces and displays them on screen without domain name or protocol resolution
- `tcpdump host IP` or `tcpdump host HOSTNAME:` Filters packets by IP address or hostname
- tcpdump src host IP: Filters packets by a specific source host
- tcpdump dst host IP: Filters packets by a specific destination host
- tcpdump port PORT_NUMBER: Filters packets by port number
- tcpdump src port PORT_NUMBER: Filters packets by the specified source port number
- tcpdump dst port PORT_NUMBER: Filters packets by the specified destination port number
- tcpdump PROTOCOL: Filters packets by protocol; examples include `ip`, `ip6`, and `icmp`
- EXAMPLES:
1.  `tcpdump -i any tcp port 22` listens on all interfaces and captures `tcp` packets to or from `port 22`, i.e., SSH traffic.
2. `tcpdump -i wlo1 udp port 123` listens on the WiFi network card and filters `udp` traffic to `port 123`, the Network Time Protocol (NTP).
3. `tcpdump -i eth0 host example.com and tcp port 443 -w https.pcap` will listen on `eth0`, the wired Ethernet interface and filter traffic exchanged with `example.com` that uses `tcp` and `port 443`. In other words, this command is filtering HTTPS traffic related to `example.com`.
- `tcpdump "tcp[tcpflags] == tcp-syn"` to capture TCP packets with only the SYN (Synchronize) flag set, while all the other flags are unset. (also available woth ack, fin, rst, push)
- `tcpdump "tcp[tcpflags] & tcp-syn != 0"` to capture TCP packets with at least the SYN (Synchronize) flag set.
- `tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"` to capture TCP packets with at least the SYN (Synchronize) or ACK (Acknowledge) flags set.


Practical exercises:
Task: How many packets in traffic.pcap use the ICMP protocol?
Command: sudo tcpdump -r traffic.pcap icmp |wc

Task: What is the IP address of the host that asked for the MAC address of 192.168.124.137?
Command: sudo tcpdump -r traffic.pcap arp -n | grep "who has 192.168.124.137"

Task: What hostname (subdomain) appears in the first DNS query?
Command: tcpdump -r traffic.pcap port 53 -n -c 1 -vv. The -r reads the file, port 53 filters DNS, -n prevents name resolution, -c 1 returns the first packet and -vv shows the verbose DNS query details (the queried hostname will be visible).

Task: How many packets have only the TCP Reset (RST) flag set?
Command: sudo tcpdump -r traffic.pcap "tcp[tcpflags] == tcp-rst" |wc

Task: What is the IP address of the host that sent packets larger than 15000 bytes?
Command: sudo tcpdump -r traffic.pcap greater 15000 -n

Task: What is the MAC address of the host that sent an ARP request?
Command: sudo tcpdump -r traffic.pcap arp -e -n
