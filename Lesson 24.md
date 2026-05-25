Module 5: Networking
Lesson 24: Nmap Basics

All the commands and scenarios I learned today:
- using `-`: If you want to scan all the IP addresses from 192.168.0.1 to 192.168.0.10, you can write `192.168.0.1-10`
- using `-`: If you want to scan all the IP addresses from 192.168.0.1 to 192.168.0.10, you can write `192.168.0.1-10`
- You can also specify your target by hostname, for example, `example.thm`
- -sn: scan the network. Example: nmap -sn 192.168.66.0/24
- -sL: will list 256 targets that can be scanned, but it doesn’t make an actual scan. It helps confirm the targets before the scan
- -sT: tries to complete TCP three way handshake with every target tcp port
- -sS: completes a “stealth” scan by sending only a first part of the three way handshake SYN
- -sU: scan of the UDP ports
- `-F` is for Fast mode, which scans the 100 most common ports (instead of the default 1000).
- `-p[range]` allows you to specify a range of ports to scan. For example, `-p10-1024` scans from port 10 to port 1024, while `-p-25` will scan all the ports between 1 and 25.
- `-p-` scans all the ports and is equivalent to `-p1-65535` and is the best option if you want to be as thorough as possible.
- Use `-p1-1023` to scan for the well-known ports.
- curl -v http://siteIP: view the websites info and body
- -O: nmap takes a guess about the operating system on the target
- -sV: detects a version of services running on targeted ports
- -A: enables OS detection, version scanning, and traceroute
- -Pn: scans hosts that appear to be down
- You can change the time of the scan with a command: T0(0,1,2,3,4,5). where 0 is the slowest and 5 is the most aggressive
- `--min-parallelism <numprobes>` and `--max-parallelism <numprobes>:` Minimum and maximum number of parallel probes
- `--min-rate <number>` and `--max-rate <number>:` Minimum and maximum rate (packets/second)
- --host-timeout: Maximum amount of time to wait for a target host
- -v: explains every step of the scan, gives verbose output [you can go up to -vvvv]
- -d: same as -v but a debugging level output [maximum level is -d9]
- `oN <filename>` - Normal output
- `oX <filename>` - XML output
- `oG <filename>` - `grep`able output (useful for `grep` and `awk`)
- `oA <basename>` - Output in all major formats

Practical:
Task: What is the last IP address that will be scanned when your scan target is 192.168.0.1/27?
Command: nmap -sL 192.168.0.1/27

Task: How many TCP ports are open on the target system at 10.112.146.247?
Command: nmap -F 10.112.146.247

Task: Find the listening web server on 10.112.146.247 and access it with your browser. What is the flag that appears on its main page?
Command adn solution: 
- With nmap -sT 10.112.146.247 found out that http port 8008 is open and listening.
- In firefox put in http://10.112.146.247:8008, and captured flag

Task: What is the name and detected version of the web server running on 10.112.146.247?
Command: nmap -sV 10.112.146.247


