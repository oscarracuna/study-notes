
source:
```
https://www.redbooks.ibm.com/redbooks/pdfs/gg243376.pdf
```

>The standard also includes [[ICMP]] (Internet Control Message Protocol) and [[IGMP]] (Internet Group Management Protocol).

IP is the protocol that hides the underlying physical network by creating a virtual network view. **It is an unreliable, best-effort, and conectionless packet delivery protocol**. Best-effort means that packets sent by IP might be lost, arrive out of order or be duplicated. **IP assumes higher layer protocols will address these anomalies**.

# IP Addressing

IP addresses are represented by a 32 bit unsigned binary value. `9.167.5.8`. Software uses the numeric value, while the symbolic names (`ibm.com`) is done by [[DNS]] (Domain Name System).

IP addressing standards are described in [[RFC 1166]].
When the host is attached to more than one network, it is called [[multihomed]] and has one IP address for each network interface..
It also consists of a pair of numbers: `<network number><host number>`.

The network number portion of the IP address is administered by one of the three [[Regional Internet Registries]] ([[RIR]]):

- [[American Registry of Internet Numbers]] ([[ARIN]]).
  In charge of North America, South America, the Caribbean and sub-Saharan Africa.
- [[Reseaux IP Europeans]] ([[RIPE]]).
  In charge of Europe, Middle East and parts of Africa.
- [[Asia Pacific Network Information Centre]] ([[APNIC]]).
  Responsible for the Asia Pacific region.

IP [[datagrams]] (the basic data packets exchanged between hosts) are transmitted by a physical network attached to the host. Each IP datagram contains a source IP and a destination IP. To send a datagram to a certain IP destination, the **target IP address** must be **translated or mapped** to a **physical address**.  <- [[Address Resolution Protocol]] ([[ARP]]). 

