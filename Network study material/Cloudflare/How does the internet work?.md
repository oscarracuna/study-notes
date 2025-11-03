

# What is the internet?
- The internet is an interconnected networks of computers that exchange date.
- Works through wires, cables and radio waves, transmitting data as bits (pulses of light or electricity).
- The more bits a line can carry, the faster the connection.


# Distributed Networking
- No central authority as it is decentralized and resilient.
- Devices can join/leave without disrupting the overall system.
- Even large-scale failures (data center outages) don't break the internet as it reroutes.


# How the internet works: Packets & Protocols
- **Packets**
	- Data is broken into packets (small chunks) with a header that gives delivery info.
	- Uses packet switching (packets that find their own paths to destination).
	- Enables massive scalability and fault tolerance.
- **Protocols**
	- Set of rules that ensure communication between different systems.
	- Most important ones are:
		- [[Ethernet]] - local delivery
		- [[IP]] (Internet protocol) - addressing and routing
		- [[TCP]] (Transmission Control Protocol) - reliable delivery
		- HTTP/HTTPS - web content delivery
		- [[UDP]] (User Datagram Protocol) - Faster (no 3 way handshake). Connection oriented. Used for streaming.



# Core Internet Infrastructure
- Routers: Direct traffic between networks.
- Switches: Direct traffic within the same network.
- Web Servers: Host and server content (HTML, video, images, apps).



# From Web Server to your Screen
1. DNS Query. Your browser asks [[DNS]] for the IP of the website.
2. TCP Handshake establishes the connection to the server.
3. [[TLS]] Handshake encrypts the connection for security.
4. HTTP Request: Browser requests the web page content.
5. HTTPS Response: Server sends packets of HTML/CSS/JS back.
6. Browser rendering: Browser assembles and displays the page.



# Helping build a better internet
- The internet wasn't originally build with security or privacy in mind.
- Cloudflare enhances it by:
	- Creating secure, fast protocols.
	- Offering privacy-first tools like 1.1.1.1 (VPN for phones, basically) and DNS over HTTPS.
	- Building global infrastructure (data centers).
	- Offering free tools to improve performance, security and reliability.

