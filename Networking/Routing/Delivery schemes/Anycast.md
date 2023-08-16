## What is anycast, and how does it work?

Anycast is a **routing method** that aims to make networks and data transfer more efficient, more reliable, and more flexible. The routing scheme is mainly used in connection with [[IPv6]], which is used as the standard method for transmitting data packets throughout computer networks (successor to IPv4).

Fact

Routing is responsible for the logistics and regulation of data transfer in networks. Data packets are sent from station to station over variable routes. At the nodes of a transport route, routers (the word “hop” is also used here) make use of the redirectable [[Index of Internet Protocol|Internet Protocol]]. The devices examine the received data packets (e.g., the information about the origin and destination of a packet is evaluated). Special tables (routing tables) with guidelines and important information about the data packets and their routing are used. If possible, the shortest route is chosen. In the event of errors or failures in the network, alternatives for transporting the data are quickly identified.

### Common IP address for a group of computers

With anycast, routing is operated in a specific way: A **group of computers** is assigned a common [[What is a IP Address]]. In terms of the goals and methods of anycast, they go strongly against the grain. With the usual method of [unicast addressing](https://www.ionos.com/digitalguide/server/know-how/unicast/ "Unicast"), **IP addresses are clearly** only assigned to a single instance (classic individual addressing).

**Multiple assignment** is not a problem, however, as it does not affect client-server communication. A client cannot distinguish between syntactically identical anycast addresses and unicast addresses. If, for example, a client makes a specific request, it generally only communicates with one anycast server from the group. This server then processes the DNS query of the client. The routing scheme only works in its intended form if the IP address that is used has also **explicitly been declared an anycast address on the corresponding routers** of an anycast network.

### Combination of anycast and BGP

The servers of an anycast network are spatially separated, meaning they can be found in different regions and countries, for example. Each anycast computer represents a corresponding route that is communicated via a routing protocol. The **BGP (Border Gateway Protocol)** is used on the Internet for such purposes, which allows for data to be transported beyond individual Internet provider networks. Through the combination of routing scheme (anycast) and BGP-based network communication, **various routing alternatives can be made available both nation- and even worldwide**.

Fact

The Border Gateway Protocol (BGP) organizes the exchange of routing information and ensures that packets can be transported as smoothly as possible over the global Internet. The protocol enables the limits of autonomous systems (such as the networks of Internet service providers) to be exceeded.

### Common use: anycast DNS

**Anycast DNS** is a frequent communication routine in a network. If, for example, a server fails during a DNS request or is currently unavailable, a certain route is no longer propagated through the anycast server network and subsequent data packets are forwarded to another server. For the alternative route, the **closest interface in a group** is usually selected in order to save time and money.

Due to the **transparency principle**, clients do not notice that the original route is no longer available. All servers respond to the client request with the same answer and the IP address used for routing does not change, although on a technical level, another instance of the anycast group is now responsible for transporting the data packet forward. The **unicast routing scheme** is often used for managing and configuring an anycast computer network. A unique unicast address is used to address individual servers directly, regardless of the ambiguous anycast address (which is assigned to several servers), and to administer them remotely via the network.

## What are the goals and advantages of anycast?

### Load sharing and failure compensation

Data exchange via anycast ensures **load sharing**, since the data traffic can be distributed over a larger area. The servers of an anycast group can even act in **different networks**. The sender does not have to take action themselves in order to distribute the data being sent as optimally as possible over many servers. **DNS root servers**, for example, benefit from this strategy of automated routing. In addition to DNS, other Internet services can also be made available worldwide and simultaneously be distributed as efficiently and evenly as possible through networks.

The **redundancy principle** also increases the availability of services. For example, anycast DNS queries are not sent to a specific DNS resolver, but to a network of resolvers. The most accessible resolver is then selected. This means that DNS queries and responses are always routed via **optimized transport routes**. If a DNS resolver goes offline, other servers are still available in the network for queries.

### Flexibility and acceleration of data transfer

The distribution principle of this routing scheme also helps with **network problems**. Especially at peak times or in the event of isolated network, interface or router failures, anycast can contribute to **accelerating data transfer** with a quickly and automatically determined alternative route, since the shortest possible routes are selected for redirecting and distributing data streams.

Companies that have multiple access points to the Internet particularly benefit from **increased flexibility**. In this way, the failure of a connection to the provider or to a router of the provider can be compensated immediately by another **transfer route via an alternative route**. With anycast routing, however, senders cannot independently select the receiving interface, as this is exclusively defined by the routing protocol.

### DDoS attack mitigation

Anycast does not only make networks and the transfer of data streams more efficient and more resistant to malfunctions and failures. **Security** also benefits from this routing scheme. [Distributed computing](https://www.ionos.com/digitalguide/server/know-how/what-is-distributed-computing/ "What is distributed computing?") (or distributed infrastructures) is usually less susceptible to hacker attacks and can often react better to them. Anycast routing is a particularly effective means against [denial of service attacks](https://www.ionos.com/digitalguide/server/know-how/what-is-dos-denial-of-service/ "What is DoS (denial of service)?") (also called DDoS attacks), which hackers can use to bring digital infrastructures to their knees.

Due to the **enormous amount of traffic** that is generated by hijacked computers and IoT devices around the world and directed specifically to the victim of an attack, overloaded websites and servers can no longer be reached, at least temporarily. The operators of websites or servers who, for example, are transacting a large online sales campaign or want to stream a significant live event are then **often blackmailed and have to buy their way out** in order to avert financial damage.

Anycast can distribute DDoS attacks over **a large area according to the diffusion principle** and thereby at least weaken them (this is comparable to the force of a raging river, which is diffused by cleverly distributing the water over floodplain areas and into distributaries). At the same time, the distribution can **limit the breadth** of the attack and continue to give many users access to the affected infrastructure via alternative routes. However, the **anycast network must be sufficiently large** and efficient to combat such attacks effectively and reliably, some of which are extremely complex.

## Comparison of different routing schemes

In addition to anycast, **other routing methods** such as [broadcast](https://www.ionos.com/digitalguide/server/know-how/broadcast-address/ "Broadcast address") are used for data traffic in a network. The following table illustrates the differences between anycast and other common routing schemes:

|Anycast|Multicast|Broadcast|Unicast|Geocast|
|---|---|---|---|---|
|With this routing method, a single computer from a whole group of computers is addressed via a special IP address (anycast address) (usually the closest server).|In this routing process, a single sender exchanges information with several receivers (group addressing).|This routing scheme addresses all recipients in a network via broadcast and can transfer data packets to all participants.|Only one recipient is addressed (classic individual addressing).|Messages are transmitted in a spatially limited area (only logged-in recipients are involved in the communication).|