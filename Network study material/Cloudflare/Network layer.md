
# What is the network layer?
It's responsible for getting data from one network to another. It enables inter-network communication.

# What happens at the network layer?
- Routing: Determines the best path for packets to reach their destination.
- Addressing: Uses [[IP]] addresses to identify source and destination devices across networks.
- Packet forwarding: Moves packets from one router to another.
- Fragmentation: Breaks up large packets to fit into smaller frames if necessary.
- Network testing and diagnostics: Uses protocols like [[ICMP]]..

# What is a packet?
- All internet traffic is sent in packets (small data chunks).
- A packet = header + data
	- Header: Contains metadata like source IP, destination IP, packet length, etc.
	- Data (Payload): The actual content being sent (e.g., part of a web page, video or email.)


# What is a network?
A network is a group of connected devices (computers, phones, servers, etc.).
Subnetworks or [[subnets]] are smaller logical divisions within networks, useful for IP management and segmentation.

| **Protocol**        | **Purpose**                                                   |
| ------------------- | ------------------------------------------------------------- |
| **IP (IPv4, IPv6)** | Main protocol that handles addressing and routing.            |
| **ICPM**            | Used for testing, errors and diagnostics (ping).              |
| **IGMP**            | Manages multicast group memberships.                          |
| **GRE**             | Tunneling protocol used to encapsulate packets.               |
| **IPsec**           | Provides secure encryption and authentication for IP packets. |

# [[OSI]] vs [[TCP/IP]] model

| **OSI Model**           | **TCP/IP Model**         |
| ----------------------- | ------------------------ |
| 7 layers                | 4 layers                 |
| More theoretical        | More practical           |
| Network Layer = Layer 3 | Internet Layer = Layer 2 |


From GPT:
The network layer is responsible for routing packets between different networks using IP addressing. It's where protocols like IP and ICMP operate and it's critical for inter-network communication. In a Zero Trust model, protecting the network layer from threats like DDoS is vital.