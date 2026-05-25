Module 5: Networking
Lesson 21: Networking Secure Protocols

1. TLS
TLS is a cryptographic protocol operating at the OSI model’s transport layer. Was originnaly founded as an improved version of the SSL.  It allows secure communication between a client and a server over an insecure network. TLS ensures that no one can read or modify the exchanged data. Protocols as HTTP, DNS, MQTT, and SIP recieved security updates with the addition of the TLS, and became HTTPS, DoT and many more with S-secure.
- First step for a server or a client is to get assigned a TLS certificate. Once the Certificate Signing Request is made, and is submitted to Certificate Authority and the digital certificate is issued, it can be used to identify the server or a client.

2. HTTPS
HTTPS is basically a HTTP over TLS. Requesting a page over HTTPS will require the following three steps:
- Establish a TCP three-way handshake with the target server
- Establish a TLS session
- Communicate using the HTTP protocol; for example, issue HTTP requests, such as GET / HTTP/1.1 
TLS will encrypt all the traffic on the stream of packets. There's no way to know the contents without acquiring the encryption key.

3. SMTPS, POP3S, IMAPS
Adding TLS to SMTP, POP3, and IMAP is no different than adding TLS to HTTP. Almost all the points from the HTTPS notes apply to these protocols.
The ports insecure versions run on:
- HTTP	80
- SMTP	25
- POP3	110
- IMAP	143
Ports the secure versions run on:
- HTTPS	443
- SMTPS	465 and 587
- POP3S	995
- IMAPS	993

4. SSH
OpenSSH offers several benefits that include:
- Secure authentication: Besides password-based authentication, SSH supports public key and two-factor authentication.
- Confidentiality: OpenSSH provides end-to-end encryption, protecting against eavesdropping. Furthermore, it notifies you of new server keys to protect against man-in-the-middle attacks.
- Integrity: In addition to protecting the confidentiality of the exchanged data, cryptography also protects the integrity of the traffic.
- Tunneling: SSH can create a secure “tunnel” to route other protocols through SSH. This setup leads to a VPN-like connection.
- X11 Forwarding: If you connect to a Unix-like system with a graphical user interface, SSH allows you to use the graphical application over the network.
To connect to an SSH server you'd issue command: ssh username@hostname.

5. SFTP and FTPS
SFTP stands for SSH File Transfer Protocol and allows secure file transfer. It is part of the SSH protocol suite and shares the same port number, 22. If enabled in the OpenSSH server configuration, you can connect using a command such as sftp username@hostname. Once logged in, you can issue commands such as get filename and put filename to download and upload files, respectively.
FTPS stands for File Transfer Protocol Secure. It is secured using TLS, and runs on the port 990. 

6. VPN
Virtual Private Network helps to establish a private network for remote (virtual) devices that need to access the shared resources as they were physically located together. VPN provides a very convenient and relatively inexpensive solution for a private and secure exchange of information. Once a VPN tunnel is established, all our Internet traffic will usually be routed over the VPN connection (VPN tunnel). When we try to access an Internet service or web application, they will not see our public IP address but the VPN server’s.

7. Practical
Task: Using Wireshark, I have to log in a remote VM, open a file, decrypt the file, and using filters find and read through the packet that contains password for a User.
Execution: 
- Opened Wireshark, found the file and opened it too.
- After clicking a TLS packet, went to the "protocol preferences", selected "transport layer security", and clicked on "open transport layer security".
- Decrypted file by selecting it in the (Pre) Master-secret log filename.
- Filtered the packets with "http2.streamid == 15" filter to find the right packet, because the needed packet was on the stream 15. Found a packet named JSON /login (name of the user).
- Opened the packet named DATA, expanded the HyperText Transfer Protocol 2, followed the TCP stream
- Found a field named Form item: "pass", got the needed password
 
