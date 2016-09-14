# NCTU-Computer-Networks
Notes and Assignment from the National Chiao Tung University (Taiwan) IOE5041 Computer Networks course


Introduction
=================


Course homepage: http://speed.cis.nctu.edu.tw/~ydlin/course/cn/mcn.html



Fundamentals
=================

Requirements
------------


**Requirements for Computer Networking**


Q: How do we frame a problem?
 >- objective: requirements
 >- constraints: principles

Q: What do we need to include in the solution
>- design: one architecture and many algorithms
>- implementation: code

Q: What do we ask about computer networks / 3 objectives of computer networks?
> - Connectivity: shared platform
> - Scalability: large number of users and applications
> - Resource-sharing: packet switching & circuit switching;  efficiency 
> *e.g. each party only talking half of the time on telephone calls*



**Connectivity: Node, Link, and Path (sequence of nodes and links)**


1. Node: host or gateway
- Host: end-point where users or applications reside
- Gateway: device to interconnect hosts

2. Link: point-to-point or broadcast
- Point-to-point: two end-points (full-duplex, half-duplex, simplex)
- Broadcast: many attach-points (need to contend for the right to transmit), normally shorter range


>Wired or Wireless
>- Wired: twisted pairs, coaxial cables, fiber optics etc
>- Wireless: radio, microwave, infrared, and beyond


3. Path: routed or switched
- Routed: stateless concatenation of links, [packet switching]
- Switched: stateful concatenation of links (hardstate vs softstate), [circuit switching]
*e.g. relationship state*

Switching is much faster than routing but at the cost of setup overhead (switching table)

 >- Circuit switching: indexing, telecom, eg ATM and phone call; switched
 >- Packet switching: matching, datacom, eg Internet and Skype call; routed

>Indexing is much faster than matching, but the overhead is that indexing >needs to establish a much larger entry table. However, matching is more >widely used, as matching has only the number of destinations as table entries, >not the number of flows/connections as entries which is much larger. (In actual >implementation, hashing is used to speed up the process).

>Circuit Switching Fall Back (CSFB): a compromise to handle both data and >voice calls; propagation delay in packet switching *e.g. delay in international >calls should be < 200ms, can be checked by ping or traceroute*



**Scalability: Number of Nodes**


Computer network: a scalable platform to *group* a large number of nodes so that each node knows how to reach any other node

*Hierarchy* of nodes (divide and conquer; currently 3-level; Internet, ~100,000 or 256*256=65,536 domain, and 256 destination sub-net etc)

LAN (local)
MAN (metropolitan)
WAN (wide)

Intra-domain and inter-domain routing have different requirements for scalability, so the solutions will be different too



**Resource Sharing**


Computer network: a **shared** platform where the capacities of nodes and links are used to carry communication messages between nodes

Q: How to share?
> - Store-and-forward packet switching (vs circuit switching)
> - Packet the message (chop message into packets and put headers)
> - Queuing/buffer, no blocking or dropping (vs circuit switching no queuing required, no packet loss or jitter/latency)
>  - at node: queuing/buffering and processing time
>  - at link: queuing/buffering, transmission, propagation time

