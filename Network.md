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
    - First bit: 0
    - First octet: 1 - 126
    - Subnet mask: 255.0.0.0
  - Class B: Produce upto 65,000 hosts -> Use for medium to large organization
    - First 2 bits: 10
    - First octet: 128 - 191
    - Subnet mask: 255.255.0.0
  - Class C: Produce up to 254 host (Because all 1s or 0s are used for broadcasting)
    - First 3 bits: 110
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
- When a device join a network, there are 4 steps for it to get an IP address
  - DHCP DISCOVER: Client send a DHCP DISCOVER message to every device on the network. This message is a broadcast 
  - DHCP OFFER: Offer an IP address to the client
  - DHCP REQUEST: Client send a message that it accept that IP address
  - DHCP ACK: Send other information to client like subnet mask, default gateway, DNS server,...

## DHCP
### What is DHCP
- DHCP (Dynamic Host Configuration Protocol) is a service that run on a server (like Microsoft server or Linux server) or router as well
- DHCP assigns IP address from its scope along with subnet mask, a default gateway, DNS server and other configuration.
- Scope: A range of IP addresses that a DHCP can give out and all the information related to the subnet that it is in
### Component of DHCP scope
- Name
- Description
- Starting IP nad Ending IP: The range of IP that DHCP can gice out
- Subnet mask
- Exclude IP: IP address that should not be assigned to new device that join the network
- Reserve IP: Specific device will be assigned the same IP address every time it join the network. DHCP recognise the device using its MAC address -> Assign the reserve IP to it. Usually given to server, printer, router,...
- DHCP server: Typiclly a server or a router that holds the network configuration
- DHCP client: The endpoint that gets the configuration information like a computing device
- DHCP Relay Agent: If there is only one DHCP for multiple LANs then DHCP relay agent will forward DHCP request to the server because DHCP packets cannot move through router
- IP address pool: Contains list of IP address which are available
- Lease time: The ammount of time for which the IP address is available to the client without renewing it
- Router address: An IP address dedicated to the router as the router address determined what subnetwork the devices are in -> Allow connection to the Internet
- DNS's name and IP
### How DHCP works
- After a certain period of time, during lease time, device will send a signal to the DHCP to renew its lease of IP address -> DHCP will know that IP address is still being used 


## Public vs private IP address
### Public IP address
- IP address that are registered on the Internet. Typically given to routers. 
- Public IP addresses are assigned by ISP
- Public IP is not free
- However, if every device has a public IP address -> Run out of IPv4 -> Use private IP address
### Private IP address
- Private IP addresses are assigned by router to devices in that network -> Device in different network can have the same private IP address
- Private IP is free
- When a device want to connect to the Internet -> Router uses NAT (Network address translation) to turn private IP address into public one
- NAT also translate public IP to private IP
- Three classes of private IP address
  - Class A: 
    - IP address: 10.0.x.x
    - Subnet mask: 255.0.0.0
  - Class B:
    - IP address: 172.16.x.x
    - Subnet mask: 255.255.0.0
  - Class C:
    - IP address: 192.168.x.x
    - Subnet mask: 255.255.255.0

## Default gateway
- A default gateway forward data from one network to another (Typically a router)
- Default: The first option that is looked up when data needs to exit a network
- If computer A and computer B are on the same network -> Computer B send its MAC address to computer A -> Two computer can communicate
- If computer A and computer B are on different network -> Computer A get the default gateway MAC address -> Send it data through the gateway -> Send its data to computer B