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
- Device connect to WiFi -> WiFi connect the device to the ISP (Internet service provider) -> The ISP connect to the network
- Ipv4: 32 bits long. 4 billion IP address (Eg: 192.8.23.127)
  - First number: Country network
  - Second number: Regional network
  - Third number: Subnetwork
  - Fourth number: The specific address of the device
- However, the Internet scale and need more IP address
- Ipv6: 128 bits long
- The DNS (Domain Name System) associates Ip address with human-friendly name
- Type a web address -> Send to a DNS -> Search for the address in the DNS cache -> Not found -> Send to a Resolver Server (ISP) -> Check cache memory for IP address -> Can't find -> Send to Root Server (13 Root Server arounf the world) -> Direct to the TLD Server(Top Level Domain) for ".com", ".net", or ".org" -> Send to the Authoritative Name Server -> Find the IP address -> Return IP address + store in cache memory

## Connection in a network
- Wire and wireless: 
  - Wire: 
    - Copper cables: Use a type of twisted pair cable -> Send pulse of electricity following the Ethernet standards to transmit data -> Also called Ethernet cable
    - Fiber-optic cables: Contain an optical fiber that carry light -> Send Pulse of light following Ethernet standards -> Transfer data much faster than copper cables
  - Wireless: A wireless card inside the computer turns binary data into radio waves -> Radio waves are picked up by wireless access point that connect to the rest of the network using cables -> Turn radio waves back into binary (Eg: WiFi)
  
## Speed of the Internet
- Bit rate: Number of bits data sent each second
- Bandwidth: Maximum bit rate of a system
  - Broadband Internet: Minimum bandwodth of 256Kbps: Enough for checking emails, reading website, but not enough for watching videos
- Latency (Ping rate): Time between sending and receiving data
  
## IPv4 address
- Each ISP has a range of IP address they can assign -> Give new IP address each time device connect to the Internet -> Called dynamic IP address
- Composed of 2 part: Network ID + Host ID
- Use subnet mask to get network ID: Bit manipulation
  - 255.0.0.0: First 8 bits are network ID
  - 255.255.0.0: First 16 bits are network ID
  - 255.255.255.0: First 32 bits are network ID
- Subnetting: Borrow bits from host ID to divide into smaller subnet
- Divide into 5 classes: First 3 classes are for commercial use
  - Class A: Produce upto 16 million host -> Use for organization with very large ammount of host (Eg: ISP)
    - First octet: 1 - 126
    - Subnet mask: 255.0.0.0
  - Class B: Produce upto 65,000 hosts -> Use for medium to large organization
    - First octet: 128 - 191
    - Subnet mask: 255.255.0.0
  - Class C: Produce up to 254 host (Because all 1s or 0s are used for broadcasting)
    - First octet: 192 - 223
    - Subnet mask: 255.255.255.0
- Subnet mask can be written in a method called CIDR (Classless Inter-Domain Routing) or slash notation. The number behind the slash is the number of 1 in the subnet mask
  - Eg: 192.168.1.0 /24
- Local loopback: 127.0.0.1 -> Access your own device
  
## Static IP address
- User assign manually
- A lot of work to make sure each device has a unique IP address if ther are many devices -> Use dynamic IP address
  
## Dynamic IP address
- DHCP (Dynamic Host Configuration Protocol) lease out IP address to device -> Device doesn't own the IP address -> If IP address is not used anymore -> Expired -> DHCP can assign that IP address to another device
- DHCP assign IP address from its scope along with subnet mask, a default gateway, and DNS server.
- Scope: A range of IP addresses that a DHCP can give out
- After a certain period of time, during lease time, device will send a signal to the DHCP to renew its lease of IP address -> DHCP will know that IP address is still being used 
- Can make reservation on DHCP using MAC address -> DHCP server will give that specific IP address everytime to that MAC address -> Usually given to server, printer, router,...
- DHCP is a service that run on a server (like Microsoft server or Linux server) or router as well

