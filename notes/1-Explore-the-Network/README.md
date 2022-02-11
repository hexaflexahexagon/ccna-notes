# 1 - Explore the Network

The very basic intro concepts of computer networking. This will primarily be a vocab & history lesson, but should give those with less exposure to networking some leads to start chasing if they so choose.

## Ways of Facilitating Data Transfers
### Clients and Servers

A client & Server architecture is a way of describing which direction information is flowing. Clients are hosts that contain software used to request and typically display information (such as Firefox). Servers are hosts that run software that can respond to requests from clients and provide info. Each different role is specialized.

TODO: diagram

### Peer-to-Peer

Peer-to-peer architecture on the other hand is one where both hosts in a conversation can be considered clients and servers simuntaneously, as both have access to programs that fulfill either role on demand.

Pros: 

- Simple design requirements
- Easy to set up a quick connection on the fly
- Cheap and doesn't need much infrastructure

Cons:

- No central administration
- Often less secure
- Not scaleable
- Usually slower

## Network Components

End devices: What the users use and care about, the start and end of a connection. Often, a personal computer on one side and a server on the other.

Intermediary devices: Connect various end devices into one, large, reachable network. Typically invisible to the average user.

- Wireless access point
- Switch
- Router
- Firewall

Network media: The mediums that communication travels across in a network.

- Metal, most commonly copper wires. Ethernet cables, Coaxial cables, phone cables.
- Glass/plastic. Fiber optic cables
- Air. Wavelengths in the electromagnetic spectrum.

## Topology Diagrams

Topology - how things are connected.

- Physical: location, wires, cable runs, OSI layer 1 devices
- Logical: devices, ports, addressing schemes

## Types of Networks

LAN - Local Area Network: Access to users and end devices in a small physical area. Small business, home, etc. Managed by an individual.

WAN - Wide Area Network: Access to other networks over a large area. Owned and managed by an entity (ISP)

WLAN - Wireless LAN (aka WAN, yes people use them interchangeably): A LAN except accessible over a wireless connection.

MAN - Metropolitan Area Network: A networked owned and maintained by a governing body proving free access to residents of the city. Spread over a medium-sized physical area.

SAN - Storage Area Network (nobody uses this term): A network designed to support file servers & provide:
1. Data storage
2. Data retrieval
3. Data replication, in case of data loss. See also: RAID arrays

## "The Internet"

A large communal project that spans (most of) the globe. Not owned or indebtted to any singlular person or organization. 

TODO: pic here

TODO: other pic here

Some people like to differentiate _the_ Internet from other _inter_net(works) by capitalizing the I like so:

- <ins>I</ins>nternet - World Wide Web
- <ins>i</ins>nternet - a group of interconnected networks

... but in reality nobody in the real world will bother with doing that.

### SOHO Internet Connections

- Cable - Offered by cable TV providers (TV + Internet over Coaxial)
- DSL - Digital Subscriber Line, runs over telephone wires, <ins>asymmetrical</ins> connection (ADSL)
- Cellular - Uses wireless cell phone network
- Satellite - Good for remote locations with no other options, but slow as dirt and needs a clear line of sight to function
- Dial-up - Cheap connection over existing telephone wires, very slow

### Business Internet Connections

Typical requirements over traditional home networks are higher burst (max) bandwidth, high dedicated (guaranteed) bandwidth, managed services (static IP).

- Dedicated Leased Lines - Reserved circuits in a SP(service provider)'s network, often over fiber optic cables, private connection guaranteed.
- Ethernet WANs - Extended LAN technology across a WAN
- DSL - Same as home DSL connections except <ins>symmetric</ins> (SDSL) upload & download speeds

## 'Separate' Networks vs Converging Networks

Separate networks are older ways of facilitating communications. Each type of tech has a different standard, different set of rules, and no way of inter-communicating. 

TODO: image

So-called 'converging' networks are the more modern way of doing things. All data is sent over the traditional TCP/IP-based network under one set of rules and constraints.

TODO: image

## Network Architecture Principals

Networks must be designed around the ideas of:

- Fault Tolerance
- Scalability
- Quality of Service
- Security

### Fault Tolerance

Limit the impact of failure (from the perspective of the user)

TODO: image

### Scalability

Provide the ability to expand services to support changing levels of demand

TODO: image

### Quality of Service

Prioritize certain data and minimize noticeable network congestion

What data? Live voice (phone calls) > Video streams > Webpages, email, everything else

Congestion occurs when demand exceeds available bandwidth, measured in bits per second (bps)

### Security

Requirements:

1. Confidentiality - only intended & authorized actors can access and read data
2. Integrity - assurance that data has not been modified in transit from source to destination
3. Availability - timely and reliable access to data and services

## New Trends

(keeping in mind these slides were probably written in 2004, as most of these are here today in one form or another)

### Business Trends

- Bring Your Own Device (BYOD): users bring in their own electronics to use on the corporate network. Cheap and convenient, but poses a security risk.
- Online Collaboration: working with others over the internet on projects at the same time. 
- Video Communication: Sending streams of video to & from anywhere at any time, high data usage requirements
- Cloud Computing: storing data over the internet in another person's data center.

4 types of "clouds":
- Public - open to the public over the internet, anybody can utilize them
- Private - not public, sometimes only accessible over the company's network
- Hybrid - two or more clouds that utilize the same architecture
- Custom - built to specific industry standards and requirements

### Home Trends

- Smart home technology: appliances that are given network-connectivity for added convenience and security risk
- Powerline networking: using existing power wiring to deliver ethernet signals.
- Wireless broadband: cell tower antenna -> roof recieving dish -> wired home network. 3G/4G/5G speeds

## Network Security

External Threats:

- Viruses, worms, trojans - ways of running malicious code on a device
- Spyware and adware - collects user information
- Zero-day / zero-hour attacks - occur too fast to be patched before infecting systems. "known by the vendor for 0 days before being released into the public"
- Hacker attacks - attacks by a knowledgeable person
- Denial of service - slow down / crash / otherwise make a device unuseable
- Data interception and theft - capture of private information
- Identity theft - using a victim's identity to steal personal information

Internal Threats:

- Lost / stolen devices
- Accidental employee misuse
- Malicious / rogue employees

Home Security Components:

- Antivirus and antispyware software - basic protection from known malware
- Firewall filtering - protect unwanted access to a home network. either host-based or router-based

Corporate Security Components:

- Dedicated firewall system - advanced, can deal with more traffic, can inspect data at higher precision
- Access control lists (ACLs) - more filtering for access on network devices based on IP addresses and port numbers
- Intrusion prevention systems - identify and prevent unknown threats based on suspect behavior
- Virtual private networks (VPNs) - give secure access to remote workstations and sites

