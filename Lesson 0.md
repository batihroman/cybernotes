Day 10 DNS and HTTP in detail.

What I did today: 
- TryHackMe room DNS in detail.
- TryHackMe room HTTP in detail.
- Practical exersises in browser.
- Learned commands used to  get info about DNS and HTTP.

What I learned today about DNS:
- What the Domanin Name System is, how it is created and used.
- What is a Top-level Domain, what is a Generic top level and a Country Code Top Level Domain, and what their purposes are.
- What is a second level domain, and that it can contain up to 63 caracters.
- What is a sub domain, what and how many caracters you can use to create it.
- What records are and their types: A record (IPv4 addresses), AAAA record (IPv6 addresses), CNAME record (resolves another domain name), MX record (servers that can handle the email for the domain), TXT record (free text fields, where you cna store any data).
- What happens when you make a DNS request and all 5 stages of it.
- Did a practical task and built a DNS request.

What I learned about HTTP:
- What is a HyperText Transfer Protocol, and what is the difference from HTTPS (secure).
- What is a URL (Uniform Resourse Locator) and what can it consist of.
- How do you make a request to the web server (GET / HTTP/1.1).
- What the responce can be and how to read the lines of that responce.
- What the HTTP methods are and 4 types of main requests (GET, POST, PUT, DELETE). 
- What the HTTP status codes are, and what the common ones mean (example- 200:OK, 404: Page not found).
- What the headers are, and what are the common ones. 
- What the cookies are, how the web server uses them, how and what for it collects data.
- Made an HTTP request with GET, DELETE, PUT, POST.

What commands I learned today:
- curl: HTTP command, sends a GET request and in responce gets body only
- curl -I: sends a HEAD rewuest, and returns headers only.
- curl -v: showsn full HTTP exchange.
- nslookup: (had to download new files for it) a DNS tool. Queries DNS server, returns IP addresses.
 
