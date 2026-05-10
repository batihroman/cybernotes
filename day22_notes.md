Section 5: Networking
Lesson 22: Wireshark basics

1. Tool Overview
Wireshark is a traffic analyser that's used for detecting and troubleshooting network problems, detecting security anomalies, such as rogue hosts, abnormal port usage, and suspicious traffic, as well as investigating and learning protocol details, such as response codes and payload data.

Practical:
- Read the comments in the given file and captured the flag.
- Found the total number of packets.
- Found the SHA256 hash value of the captured file.
- Found out the arrival date of the packet.
- Found it's TTL value.
- Found the number of warnings

2. Packet Dissection
Packet dissection is also known as protocol dissection, which investigates packet details by decoding available protocols and fields.
OSI layers in the packets: 
- The Frame (Layer 1): This will show the source and destination MAC Addresses; from the Data Link layer of the OSI model.
- Source (MAC) (Layer 2):This will show the source and destination IPv4 Addresses; from the Network layer of the OSI model.
- Protocol (Layer 4):This will show details of the protocol used (UDP/TCP) and source and destination ports; from the Transport layer of the OSI model.
- Protocol Errors:This continuation of the 4th layer shows specific segments from TCP that needed to be reassembled.
- Application Protocol (Layer 5):This will show details specific to the protocol used, such as HTTP, FTP,  and SMB. From the Application layer of the OSI model.
- Application Data: This extension of the 5th layer can show the application-specific data.

3. Packet Investigation
- Learned how to use "go to packet" feature
- Learned how to use "find packet" menu
- Learned how to mark packets
- Learned how to comment packets
- Learned how to export packets
- Learned how to export objects (files)
- Learned what is a time display format and how to change it
- Learned what is an expert info, and what all colour in it mean
Chat	Blue	Information on usual workflow.
Note	Cyan	Notable events like application error codes.
Warn	Yellow	Warnings like unusual error codes or problem statements.
Error	Red	Problems like malformed packets.

Practical:
Task: Use the "Exercise.pcapng" file to answer the questions. Search the "r4w" string in packet details. What is the name of artist 1?
- Using the given file, filtered packets with "r4w" string, opened the file, and in the HyperText field found the name of the person that I was looking for.

Task: Go to packet 12 and read the packet comments. What is the answer?
Note: use md5sum <filename> terminal command to get MD5 hash
- Went to packet 12, as the question told me, and read the comments to the packet. Comment told me to go to the packet number 39765.
- In the packet, found the data that contains a JPEG image data, saved the image to the desctop. 
- In the terminal ran "cd desktop", and "ls" to see if I saved the image. Ran "md5sum image.jpg"
- Got the needed MD5 hash.

Task: There is a ".txt" file inside the capture file. Find the file and read it; what is the alien's name?
- In the "content type" column found "text/plain". Found the file and saved it as file.txt.
- In the terminal ran "cd to the folder with file" and then "cat file.txt".
- After reading it found the name of the alien.

4. Packet filtering
- Learned what is a Apply as Filter feature.
- Learned what is a conversation filter.
- Learned how to colourise a conversation.
- Learned how to prepare as filter
- Learned how to apply as column.
- Learned how to follow a stream.
- Learned simple display filter queries such as filter by protocol name or port, filter by protocol number, filter by IP. 
