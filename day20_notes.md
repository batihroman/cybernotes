Module 5: Networking
Lesson 20: Netwoking Core Protocols

1. DNS
Maps a domain name to an IP address, so we don't have to remeber IPs. Operates on the Application layer 7. Uses UDP port 53 by default and TCP port 53 as a default fallback.
Main 4 types of DNS records:
- A record: The A (Address) record maps a hostname to one or more IPv4 addresses.
- AAAA Record: The AAAA record is similar to the A Record, but it is for IPv6.
- CNAME Record: The CNAME (Canonical Name) record maps a domain name to another domain name. For example, www.example.com can be mapped to example.com or even to example.org.
- MX Record: The MX (Mail Exchange) record specifies the mail server responsible for handling emails for a domain.

"whois": Is a command line in Linux for looking up all the information about an owner of a certain domain.

2. HTTP(S) 
A protocol that's used for browsers. This protocol relies on TCP and defines how your web browser communicates with the web servers. Commonly uses port TCP 80 and 443, and less comonly some others as 8080 and 8443
Commands that a web browser commonly issues to web server:
- GET retrieves data from a server, such as an HTML file or an image.
- POST allows us to submit new data to the server, such as submitting a form or uploading a file.
- PUT is used to create a new resource on the server and to update and overwrite existing information.
- DELETE: as the name suggests, is used to delete a specified file or resource on the server.
To get file.html, you would send GET /file.html HTTP/1.1, for instance (GET /file.html might work depending on the web server in use).

3. FTP
File Transfer Protocol (FTP) is designed to transfer files.FTP is very efficient for file transfer, and when all conditions are equal, it can achieve higher speeds than HTTP. It listens on TCP port 21 by default.
Commands that are defined by the FTP protocol are:
- USER is used to input the username
- PASS is used to enter the password
- RETR (retrieve) is used to download a file from the FTP server to the client.
- STOR (store) is used to upload a file from the client to the FTP server.

- Practical:
Connected to the FTP server using the local ftp client with the command "ftp MACHINE IP"
Issued ls for a list of files available
Switched to ASCII mode with "type ascii" to get a text file
Used command "get neededfile.txt" to retrieve the file I wanted, and found flag in it later.

4. SMTP: Email sender
Simple Mail Transfer Protocol (SMTP) is a protocol used for sending Emails. Runs on TCP port 25 by default.
Some of the commands used by a mail client when it transfers an email to an SMTP server
- HELO or EHLO initiates an SMTP session
- MAIL FROM specifies the sender’s email address
- RCPT TO specifies the recipient’s email address
- DATA indicates that the client will begin sending the content of the email message
- . is sent on a line by itself to indicate the end of the email message

5. POP3: Email reciever
The Post Office Protocol version 3 (POP3) is designed to allow the client to communicate with a mail server and retrieve email messages. Runs on TCP port 110 by default.
Some common POP3 commands are:
- USER "username" identifies the user
- PASS "password" provides the user’s password
- STAT requests the number of messages and total size
- LIST lists all messages and their sizes
- RETR "message_number" retrieves the specified message
- DELE "message_number" marks a message for deletion
- QUIT ends the POP3 session applying changes, such as deletions

Practical: 
- Connacted to a POP3 server using given credentials with a command "telnet MACHINE_IP 110, and entered credentials.
- Used PASS, STAT, LIST and then RETR 3 to retrieve a flag.

6. IMAP: synchonizing Email
Internet Message Access Protocol (IMAP) is a protocol for maintaining a synchronized mailbox across multiple devices. IMAP allows synchronizing read, moved, and deleted messages. Listens on the TCP port 143 by default.
The IMAP protocol most common commands:
- LOGIN "username" "password" authenticates the user
- SELECT "mailbox" selects the mailbox folder to work with
- FETCH "mail-number" "data-item-name" Example fetch 3 body[] to fetch message number 3, header and body.
- MOVE "sequence-set" "mailbox" moves the specified messages to another mailbox
- COPY "sequence-set" "data-item-name" copies the specified messages to another mailbox
- LOGOUT logs out
