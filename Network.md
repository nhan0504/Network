# Network
## What is the Internet
- Computer network: Any group of interconnected computing devices capable of sending and receiving data. 
- Computing device: Any device that can run a program
- The Internet: An open computer network that any device can join.
- Devices are connected to each other. 
- There was no standard rules for network to communicate -> Invent the Internetworking protocol (IP)
- Each device has a unique IP address -> Use to identify each device on the Internet
## Type of network
- LAN (Local area network): Cover a limited area (Eg: houe, school,...)
- WAN (Wide area network): Extend over a large geograpghic area. Comppsed of many LANs
- DCN (Data Center Network): Use in data senter to exchange data fast
## How the Internet work
- Device connect to Wifi -> Wifi connect the device to the ISP (Internet service provider) -> The ISP connect to the network
- Ipv4: 32 bits long. 4 billion IP address (Eg: 192.8.23.127)
  - First number: Country network
  - Second number: Regional network
  - Third number: Subnetwork
  - Fourth number: The specific address of the device
- However, the Internet scale and need more IP address
- Ipv6: 128 bits long
- The DNS (Domain Name System) associates Ip address with human-friendly name
- Type a web address -> Send to a DNS -> Search for the address in the DNS cache -> Not found -> Send to a Resolver Server (ISP) -> Check cache memory for IP address -> Can't find -> Send to Root Server (13 Root Server arounf the world) -> Direct to the TLD Server(Top Level Domain) for ".com", ".net", or ".org" -> Send to the Authoritative Name Server -> Find the IP address -> Return IP address + store in cache memory

## How to create a network
- Wire and wireless: 
- IP
- TCP/UDP
- TLS
- HTTP and DNS