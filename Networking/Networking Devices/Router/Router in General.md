## What is a router?

A router is a device that connects two or more packet-switched networks or subnetworks. It serves two primary functions: managing traffic between these networks by forwarding [data packets](https://www.cloudflare.com/learning/network-layer/what-is-a-packet/) to their intended [IP addresses](https://www.cloudflare.com/learning/dns/glossary/what-is-my-ip-address/), and allowing multiple devices to use the same Internet connection.

There are several types of routers, but most routers pass data between [LANs (local area networks)](https://www.cloudflare.com/learning/network-layer/what-is-a-lan/) and [WANs (wide area networks)](https://www.cloudflare.com/learning/network-layer/what-is-a-wan/). A LAN is a group of connected devices restricted to a specific geographic area. A LAN usually requires a single router.

A WAN, by contrast, is a large network spread out over a vast geographic area. Large organizations and companies that operate in multiple locations across the country, for instance, will need separate LANs for each location, which then connect to the other LANs to form a WAN. Because a WAN is distributed over a large area, it often necessitates multiple routers and switches*.

*_A [network switch](https://www.cloudflare.com/learning/network-layer/what-is-a-network-switch/) forwards data packets between groups of devices in the same network, whereas a router forwards data between different networks._

## How does a router work?

Think of a router as an air traffic controller and data packets as aircraft headed to different airports (or networks). Just as each plane has a unique destination and follows a unique route, each packet needs to be guided to its destination as efficiently as possible. In the same way that an air traffic controller ensures that planes reach their destinations without getting lost or suffering a major disruption along the way, a router helps direct data packets to their destination IP address.

In order to direct packets effectively, a router uses an internal routing table — a list of paths to various network destinations. The router reads a packet's header to determine where it is going, then consults the routing table to figure out the most efficient path to that destination. It then forwards the packet to the next network in the path.

To learn more about [IP](https://www.cloudflare.com/learning/network-layer/internet-protocol/) routing and the protocols that are used during this process, read [What is routing?](https://www.cloudflare.com/learning/network-layer/what-is-routing/)

## What is the difference between a router and a modem?

Although some Internet service providers (ISPs) may combine a router and a modem within a single device, they are not the same. Each plays a different but equally important role in connecting networks to each other and to the Internet.

A router forms networks and manages the flow of data within and between those networks, while a modem connects those networks to the Internet. Modems forge a connection to the Internet by converting signals from an ISP into a digital signal that can be interpreted by any connected device. A single device may plug into a modem in order to connect to the Internet; alternately, a router can help distribute this signal to multiple devices within an established network, allowing all of them to connect to the Internet simultaneously.

Think of it like this: If Bob has a router, but no modem, he will be able to create a LAN and send data between the devices on that network. However, he will not be able to connect that network to the Internet. Alice, on the other hand, has a modem, but no router. She will be able to connect a single device to the Internet (for example, her work laptop), but cannot distribute that Internet connection to multiple devices (say, her laptop and her smartphone). Carol, meanwhile, has a router and a modem. Using both devices, she can form a LAN with her desktop computer, tablet, and smartphone and connect them all to the Internet at the same time.

## What are the different types of routers?

In order to connect a LAN to the Internet, a router first needs to communicate with a modem. There are two primary ways to do this:

- _Wireless router:_ A wireless router uses an Ethernet cable to connect to a modem. It distributes data by converting packets from binary code into radio signals, then wirelessly broadcasts them using antennae. Wireless routers do not establish LANs; instead, they create WLANs (wireless local area networks), which connect multiple devices using wireless communication.
- _Wired router:_ Like a wireless router, a wired router also uses an Ethernet cable to connect to a modem. It then uses separate cables to connect to one or more devices within the network, create a LAN, and link the devices within that network to the Internet.

In addition to wireless and wired routers for small LANs, there are many specialized types of routers that serve specific functions:

- _Core router:_ Unlike the routers used within a home or small business LAN, a core router is used by large corporations and businesses that transmit a high volume of data packets within their network. Core routers operate at the "core" of a network and do not communicate with external networks.
- _Edge router:_ While a core router exclusively manages data traffic within a large-scale network, an edge router communicates with both core routers and external networks. Edge routers live at the "edge" of a network and use the [BGP (Border Gateway Protocol)](https://www.cloudflare.com/learning/security/glossary/what-is-bgp/) to send and receive data from other LANs and WANs.
- _Virtual router:_ A virtual router is a software application that performs the same function as a standard hardware router. It may use the Virtual Router Redundancy Protocol (VRRP) to establish primary and backup virtual routers, should one fail.

## What is an SSID?

SSID stands for "service set identifier," and it is the technical term for the name of the network that WLAN routers broadcast. SSIDs enable users to find and connect to the wireless network broadcast by the router (a properly secured router should require password entry as well). Consumer routers for WiFi networks usually have their factory-default SSID printed on the side or bottom.

## What are some of the security challenges associated with routers?

**Vulnerability exploits:** All hardware-based routers come with automatically installed software known as firmware that helps the router perform its functions. Like any other piece of software, router firmware often contains vulnerabilities that cyber attackers can exploit (one [example](https://threatpost.com/netgear-zero-day-takeover-routers/156744/)), and router vendors periodically issue updates to patch these vulnerabilities. For this reason, router firmware needs to be updated regularly. Unpatched routers can be compromised by attackers, enabling them to monitor traffic or use the router as part of a [botnet](https://www.cloudflare.com/learning/ddos/what-is-a-ddos-botnet/).

**DDoS attacks:** Small and large organizations often are the targets of distributed denial-of-service (DDoS) attacks directed at their network infrastructure. Unmitigated [network layer DDoS attacks](https://www.cloudflare.com/learning/ddos/layer-3-ddos-attacks/) can overwhelm routers or cause them to crash, resulting in network downtime. [Cloudflare Magic Transit](https://www.cloudflare.com/magic-transit/) is one solution for protecting routers and networks from these kinds of DDoS attacks.

**Administrative credentials**: All routers come with a set of admin credentials for performing administrative functions. These credentials are set to default values, such as "admin" as the username and "admin" as the password. The username and password should be reset to something more secure as soon as possible: attackers are aware of the common default values for these credentials and can use them to gain control of the router remotely if they are not reset.