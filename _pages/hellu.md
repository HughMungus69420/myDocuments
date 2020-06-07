---
layout: page
title: Two
permalink: /two/
---
Chapter 4

Internet Architectures

Abstract
========

In order to explain how the Internet works, this chapter takes a closer
look at the architecture that underlies the Internet, as well as at its
architectural principles and mechanisms. After providing a brief
overview of the Internet's history, this chapter examines today's core
infrastructure and explains the role of Internet service providers. In
addition, the essential mechanisms enabling Internet communication are
explained, namely the Internet Protocol (IP) suite, IP addresses, the
domain name system (DNS), as well as IP packet routing and forwarding.
This chapter also explains how large content providers, like Google,
Amazon, and Netflix, provide Internet users all over the world with
efficient and reliable services by utilizing specialized content
delivery networks. The description of four emerging architectural
concepts that extend the established Internet architecture with more
efficient and/or effective ways of providing innovative Internet
services (i.e., softwaredefined networking, network function
virtualization, overlay networks, and information-centric networking)
conclude this chapter.

Learning Objectives of this Chapter
===================================

The main learning objective of this chapter is to understand the
structure and the inner workings of today's Internet architecture. After
studying this chapter, readers will understand the key organizations
that keep the Internet running and how these players interact with one
another. From a technical perspective, readers will learn how messages
are exchanged by means of the Internet\'s network infrastructure, which
includes understanding important Internet protocols, how domain names
function, and messages' routing between their senders and receivers.
Readers will also learn about the mechanisms that help deliver content
simultaneously and efficiently to a large number of Internet users.
Finally, readers will understand what allows the Internet to evolve
continuously and the emergent architectural concepts that fuel this
process.

Structure of this Chapter
=========================

This chapter about Internet architectures is structured as follows: The
first two sections introduce the fundamental Internet concepts,
including a brief overview of the most important milestones in the
Internet's history and an introduction to the

© Springer Nature Switzerland AG 2020 83

A. Sunyaev, Internet Computing,
https://doi.org/10.1007/978-3-030-34957-8\_4

structure and governance of the Internet\'s network infrastructure. The
second section covers the IP suite, which enables communication between
Internet participants. Consequently, the IP suite's individual
components are introduced, their interactions explained, and IP
addresses' structure and purpose are introduced. Building on this, the
more advanced concepts, namely domain name resolution and IP routing,
are explained. The third section explains how content delivery networks
work, the different types, and how they differ from one another.
Concluding this chapter, the last section sheds light on four emergent
Internet network architecture concepts.

4.1 History of the Internet
===========================

The origins of today's Internet go back to the U.S. Department of
Defense's intention to ensure communication in the aftermath of a
conventional or even nuclear strike during the Cold War. The Soviet
Union's launch of its first orbiting satellite, Sputnik, in 1957 aroused
the U.S. military's concerns about attacks from space. At that time, the
national defense network relied on the public telephone system, which a
single orbital strike could easily disrupt. To mitigate this and similar
national security threats, the Advanced Research Projects Agency (ARPA),
today known as the Defense Advanced Research Projects Agency, was
founded on February 7, 1958. In 1962, an ARP scientist (J.C.R.
Licklider) developed a first concept for connecting multiple computer
systems to form a long-distance communications network that would keep
operating even in the event of a nuclear attack. In 1965 the invention
of packet switching technology, which allowed for reliable data
transmission and provided an early form of routing devices (i.e.,
interface message processors), complemented the computer network idea.
Based on these key technology advancements, the ARPA completed the first
version of the ARPANET in 1969. On November 21, 1969 the first link was
established between the University of California, Santa Barbara's and
the Stanford Research Institute's computer systems via the ARPANET. Less
than two weeks later, on December 5, 1969, another two nodes joined the
network (University of California, Los Angeles and the University of
Utah).

In 1971, Ray Tomlinson sent the first email between two computers over
the ARPANET. Two years later, the ARPANET expanded internationally by
connecting the University College of London (England) and the Royal
Radar Establishment (Norway). In 1974, Vinton Cerf and Robert Kahn,
later referred to as the fathers of the Internet, published \"A Protocol
for Packet Network Interconnection,\" (Cerf and Kahn 1974) detailing the
design of the Transmission Control Protocol (TCP), an important part of
today's Internet protocol stack (see section 4.3). The first attested
use of the term Internet an abbreviation for internetworking (i.e., the
interconnection of two heterogeneous networks) is found in the TCP's
formal specification (Cerf and Sunshine 1974).

4.1 History of the Internet

In 1981, the National Science Foundation (NSF) indirectly opened up the
ARPANET to computer science institutions by creating the Computer
Science Network (CSNET), which eventually comprised more than 180
institutions (Stewart 2000). While not all institutions could be
directly connected to the ARPANET due to technical and organizational
limitations, the few universities that were part of both ARPANET and
CSNET acted as gateways to the networks. Two years later, in 1983, the
ARPANET was restructured and divided into a highly secured military
network (MILnet) and an open civil network (ARPANET), which remained
connected by means of controlled gateways. In the same year, the ARPANET
officially adopted the open networking protocols TCP and the Internet
Protocol (IP), which, combined, are called TCP/IP. Owing to TCP/IP's
simplicity and scalability, it removed the existing capacity constraints
and allowed almost any network to be connected to the ARPANET,
irrespective of their local characteristics (Kozierok 2005; Fall and
Stevens 2011). Based on this technology, the NSF created a new network,
the NSFNet, in 1984 to connect to its supercomputer centers located at
various U.S. universities (Frazer et al. 1996). Soon after its launch,
numerous smaller university networks across the U.S. and the rest of the
world connected to the NSFNet, including the ARPANET. Owing to its rapid
growth, the NSFNet took on the role of the U.S. Internet backbone[^1],
which interconnected the different regional networks to the one large
network, today referred to as the Internet, in 1988 (Mills and Braun
1987). As just one of many Internet subnets, the ARPANET started losing
its relevance, leading to its decommission in 1990.

In 1989, Tim Berners-Lee created the hypertext transfer protocol (HTTP)
at the European Organization for Nuclear Research, which in turn led to
the development of the first Web browser called the WorldWideWeb. This
was the birth of the World Wide Web (WWW), which, from today's
perspective, indicates a far broader term than just a Web browser.
Finally, in 1995, the NSFNet modified its acceptable use policy in terms
of applying the network for commercial use and, soon after, it was
gradually replaced by backbones operated by commercial Internet service
providers (ISPs). At the same time, ISPs, like Compuserve and America
Online, also started building network access points that allowed the
Internet's commercialization and privatization.

The rest is history in the making. Over the past 60 years, the Internet
has evolved from a simple research concept to a technology which more
than four billion people currently use and which continues to evolve
through the development of novel ideas, services, and architectures.

4.2 Today's Internet Network Infrastructure
===========================================

The Internet is a large network of computer networks that connects
billions of computing devices around the globe. Each of these devices
can communicate with any other computing device as both are connected to
the Internet and use the same communication protocols.

Computer Networks
-----------------

Understanding the concept of computer networks is paramount to
understanding the Internet's architecture as we know it. A computer
network is a collection of interconnected devices for electronic data
communication (NIST 2013; Mansfield and Antonakos 2009). In terms of its
physical structure, a computer network consists of linked network
devices (i.e., nodes) that either serve as endpoints (e.g., servers,
personal computers, or smartphones) or network devices that facilitate
the relaying of data between endpoints (e.g., modems, hubs, bridges and
switches). Network nodes rely on standardized communication protocols to
exchange information and to transport data to their intended endpoint.
Such communication protocols define the way in which data should be sent
and received precisely. Modern Using either wired or wireless
technologies computer networks connected to the Internet are often based
on the TCP/IP protocol suite, which will be explained in detail in
section 4.3.

Computer Network
----------------

> A computer network is a collection of computers and devices connected
> for the purpose of electronic data communication that allows them to
> share information and services (Mansfield and Antonakos 2009; NIST
> 2013).

Computer networks may be private or public. Private networks allow only
authorized nodes to access the network and communicate with other
connected nodes. Depending on the particular network configuration, a
node can identify itself by means of credentials (e.g.,
username/passwords or certifications) or is granted access by a network
administrator. In contrast, with no or only a few exceptions, any node
can access public networks. While the resulting openness facilitates
communication between nodes, it also makes it easy for malicious nodes
to join the network, which increases the security risks compared to
those of private networks.

The geographical distance between individual nodes also categorizes
computer networks. A local area network (LAN) connects nodes in close
proximity, for instance, within the same room, on the same floor, or in
the same building. Nodes that are further apart, but still confined to a
50 km radius, are linked by a metropolitan area network (MAN) (Gokhale
2005). If the distance between nodes exceeds 50 km, they are
interconnected via a wide area network (WAN), which is usually not
restricted to an enclosed geographical space. As shown in Table 4.1,
longer distances between nodes comes at the cost of lower transmission
rates and higher propagation delays due to the underlying transmission
medium's physical limitations. Using

either wired or wireless technologies (or a mixture of both) allows for
establishing a connection between individual network nodes. A wired
network connection uses transmission media like copper or optical fiber
cables. Wireless networks can be based on a variety of transmission
methods, like radio, microwaves, or optical signals (e.g., lasers).

Table 4.1 Overview of Computer Network Types

+--------------+----------------+----------------+----------------+
|              | > Wide Area    | > Metropolitan | > Local Area   |
|              | > Network      | > Area         | > Network      |
|              |                | >              |                |
|              |                | > Network      |                |
+==============+================+================+================+
| Abbreviation | > WAN          | > MAN          | > LAN          |
+--------------+----------------+----------------+----------------+
| Purpose      | > Connects     | >              | > Connects     |
|              | > computing    |  Interconnects | > computing    |
|              | > devices over | > computing    | >              |
|              | > a large      | > devices      | > devices      |
|              | > geographical | > within a     | > within the   |
|              | > distance or  | > city or      | >              |
|              | > even those   | > metropolitan | > same room or |
|              | > across the   | > area         | >              |
|              | > globe        |                | > building     |
+--------------+----------------+----------------+----------------+
| Geographic   | > More than 50 | > 5 to 50 km   | > Less than 5  |
|              | > km           |                | > km           |
| Expanse      |                |                |                |
+--------------+----------------+----------------+----------------+
| Transmission | > Low          | > Medium       | > High         |
|              |                |                |                |
| Rates        |                |                |                |
+--------------+----------------+----------------+----------------+
| Propagation  | > High         | > Medium       | > Low          |
|              |                |                |                |
| Delay        |                |                |                |
+--------------+----------------+----------------+----------------+
| Applications | > Networks     | > City         | > Industrial   |
|              | > between      | > networks,    | > plants,      |
|              | > globally     | > several      | > business     |
|              | > distributed  | > industrial   | > offices,     |
|              | > enterprise   | > facilities   | > university   |
|              | > branches,    | > in close     | > campuses,    |
|              | > the Internet | > proximity    | > domestic     |
|              |                |                | > homes        |
+--------------+----------------+----------------+----------------+

The Internet -- A Network of Networks
-------------------------------------

Given the description of computer networks, the Internet can be defined
as a public wide area network based on the TCP/IP protocol suite to
interconnect computer systems across the world. Nodes connected to the
Internet provide a large variety of information resources and enable
services, such as e-mail, voice over IP, peer-topeer file sharing, and,
of course, the meta-service WWW. It is important to emphasize that the
terms Internet and WWW are not synonymous. The WWW, or simply the 'Web,'
is just one service that the Internet provides. The WWW is basically a
set of resources (e.g., webpages, documents, and images) connected by
hyperlinks and accessed via Uniform Resource Identifiers (URIs)
(Berners-Lee et al. 2004). Further, while the well-known Hypertext
Transfer Protocol (HTTP) and its extension, the Hypertext Transfer
Protocol Secure (HTTPS) are essential for data exchange via the WWW,
they are only two of various protocols used for communication on the

Internet.

World Wide Web
--------------

> The World Wide Web (WWW, or simply the Web) is an information space
> (on the Internet) in which global identifiers called Uniform Resource
> Identifiers identify the items of interest, referred to as resources
> (Berners-Lee et al. 2004).

At the beginning of this chapter, the Internet was described as a
network of computer networks. Even though, from users' perspective, the
Internet does seem like one large network, its fragmented structure
becomes obvious when taking a closer look at its actual topology. Fig.
4.1 presents a simplified depiction, in which the Internet is a
hierarchically structured network of numerous WANs.

The global Internet backbone, a network that links independent WANs from
different areas of the world, known as Internet regions, resides at the
highest hierarchy level (or tier) (Norton 2011). These WANs are usually
operated by large national telecommunication companies referred to as
tier 1 ISPs (i.e., Internet Service Providers) or Backbone Internet
Providers. Tier 1 ISPs, like AT&T, CenturyLink, and Deutsche Telekom,
use the global Internet backbone to exchange data traffic across
Internet regions. This means that if a node A located in one Internet
region sends data to a node B in another Internet region, the
transmission will, at some point, cross the border between the regions
by being passed from a tier 1 ISP responsible for A's internet region to
a tier 1 ISP responsible for B's internet region. This exchange of data
traffic between two ISPs is called peering. In most cases, peering
between tier 1 ISPs is carried out over high-speed optical fiber cables
that either interconnect their networks (private peering) directly, or
are brought together for public peering in an Internet Exchange Point
(IXP), which is a provider-neutral data center where several ISPs
connect with one another to exchange data traffic.

Since peering across Internet regions has high infrastructure
requirements (e.g., submarine cables or communication satellites) and
high demands regarding the provider\'s organizational and technical
capabilities, the vast majority of today's ISPs reside on tier 2 and 3
of the Internet's topology. These lower-tier ISPs often act as middlemen
between their end-customers (e.g., businesses and consumers) and other
ISPs by relaying Internet traffic within the same Internet region.

To this end, tier 2 ISPs (regional ISPs) operate their own networks. If
two communicating nodes are connected to the same tier 2 network, the
relevant ISP delivers data transmissions between them directly without
ever leaving its network. If two nodes are connected to different ISP
networks in the same Internet region, the relevant two ISPs will engage
in peering, either directly or indirectly, over additional ISP networks
on the path between the nodes. Similar to cross-regional peering,
peering within an Internet region is either handled privately (i.e.,
directly) between two ISPs, or over a Metropolitan Area Exchange (MAE),
which is a regional version of an IXP operated in densely populated
areas. In order to relay data to and from other Internet regions, tier 2
ISPs need to engage in peering with a tier 1 ISP in their region. This
process may involve fees for the lower tier ISP. Although ISPs on the
same tier usually do not charge one another for transit, upstream
peering from lower to higher tier ISPs creates fees for the lower tier
ISP if no other peering agreements was closed.

Tier 3 ISPs (local ISPs) only operate by purchasing data transit from
tier 1 and 2 providers, and do not engage in peering between one
another. Tier 3 ISPs are specialized in connecting residential homes and
businesses with the Internet. However, the boundaries between tier 2 and
tier 3 ISPs are blurred and the terms are sometimes used interchangeably
due to their similar proximity to the end-customer

> ![](media/image2.png){width="4.323333333333333in"
> height="7.183333333333334in"}

business. Furthermore, some organizations operating large networks
(e.g., universities, global enterprises, and government institutions)
often bypass tier 2 and 3 ISPs by directly engaging themselves in
peering and transit purchasing.

Internet users may be ISP customers on any of the Internet's topology's
tiers. In order to access their ISP's services, customers' nodes need to
establish a connection to the ISP's network. This is done over either a
wired (e.g., telephone system) or wireless (e.g., satellite link or cell
phone network) connection that ends at the ISP's nearest physical access
point. Such access points, or points of presence (POPs), are often
located within the facility of the telecommunications provider
responsible for the physical communication infrastructure to the
customer. Finally, the POPs are connected to the relevant ISP's network,
which, as described above, provides direct or indirect access to the
global Internet backbone.

Fig. 4.2 provides a simplified depiction of how two nodes in different
Internet regions are connected over ISP networks. An Internet user,
whose computer is connected via a landline to the POP of her tier 2 ISP,
initiates the transmission in the example. The tier 2 ISP detects that
the transmission's destination is not within its network, nor in the
same Internet region, therefore relaying it to the relevant tier 1 ISP.
The tier 1 ISP then engages in peering over an IXP with a tier 1 ISP
responsible for the destination Internet region. Within the destination
region, the transmission is again relayed to the receiving node's tier 2
ISP. A local POP establishes the connection between the tier 2 ISP and
the destination endpoint, finally delivering the transmission.

> ![](media/image3.png){width="4.569972659667542in"
> height="2.043977471566054in"}

Fig. 4.2 Internet Connection Example

Regulation of the Internet
--------------------------

Several organizations standardize, manage, and advance the various
facets of the Internet. Table 4.2 provides a list of the most important
organizations, which are detailed in the remainder of this section.

The Internet Society (ISOC) takes a central role in the Internet's
development and technical evolution. The ISOC is a nonprofit
organization providing consulting for Internet-related public policy,
training for individuals, and serves as an umbrella organization for the
groups responsible for Internet standards and technologies, including
the Internet Engineering Task Force (IETF), the Internet Research Task
Force (IRTF), and the Internet Architecture Board (IAB). The IAB is a
technical advisory board entrusted with the task of overseeing the
architectural development of the Internet, which includes supervising
the IRTF and IETF (Chapin 1992). The IRTF researches future Internet
technologies to solve basic technical problems and drives the Internet's
long-term evolution (Falk 2009). When new technologies are ready for
implementation, they are passed on to the IETF, which is an open
standards organization tasked with maintaining and developing Internet
technology further. The IETF is particularly concerned with the
standardization of the communication protocols used on the Internet,
such as the IP, User Datagram Protocol (UDP), TCP, Stream Control
Transmission Protocol (SCTP), and HTTP.

The Internet Corporation for Assigned Names and Numbers (ICANN) is a
non-profit corporation whose primary role is to oversee the IP address
and domain name space. The ICANN delegates the administration and
registration of IP addresses and address spaces to five Regional
Internet Registries, namely the African Network Information Center
(AFRINIC), the American Registry for Internet Numbers (ARIN), the
Asia-Pacific Network Information Centre (APNIC), the Latin America and
Caribbean Network Information Centre (LACNIC), and the Réseaux IP
Européens Network Coordination Centre (RIPE NCC). In addition, the ICANN
oversees and manages the domain name system (DNS; see section 4.3.3).
All domain names used on the Internet, such as
[google.com](http://google.com/) and [amazon.com](http://amazon.com/),
are assigned by means of a registration process that local registrars
accredited by the ICANN undertake. The ICANN is also responsible for
introducing new top-level generic domains, like .app and .news.

The World Wide Web Consortium (W3C) is responsible for developing
interoperable technologies (specifications, guidelines, software, and
tools) for the WWW. The W3C's primary purpose is to ensure the WWW is as
accessible as possible to "all people, whatever their hardware,
software, network infrastructure, native language, culture, geographical
location, or physical or mental ability." (W3C 2017) To this end, the
W3C maintains well-known Web technology standards, for instance, the
Hypertext Markup Language (HTML), the Extensible Markup Language (XML),
and Cascading Style Sheets (CSS).

Table 4.2 Organizations for Standardization and Regulation of the
Internet (selection)

+----------------------------------+----------------------------------+
| Organization                     | > Main purpose                   |
+==================================+==================================+
| The Internet Society (ISOC)      | > Provides the organizational    |
|                                  | > structure that supports the    |
|                                  | > process of Internet standard   |
|                                  | > development                    |
+----------------------------------+----------------------------------+
| Internet Research Task Force     | > Researches solutions for basic |
| (IRTF)                           | > technical problems and the     |
|                                  | > Internet's long-term evolution |
+----------------------------------+----------------------------------+
| Internet Engineering Task Force  | > Develops and maintains         |
|                                  | > Internet technology standards  |
| (IETF)                           | >                                |
|                                  | > (e.g., TCP/IP)                 |
+----------------------------------+----------------------------------+
| Internet Architecture Board      | > Architectural oversight of the |
| (IAB)                            | > Internet development           |
|                                  | >                                |
|                                  | > (e.g., oversight of IETF and   |
|                                  | > IRTF)                          |
+----------------------------------+----------------------------------+
| Internet Corporation for         | > IP address space allocation    |
| Assigned                         | > and management of the domain   |
|                                  | > name system                    |
| Names and Numbers (ICANN)        |                                  |
+----------------------------------+----------------------------------+
| Regional Internet Registries     | > Administration and             |
| (RIR)                            | > registration of IP address     |
|                                  | > spaces for individual Internet |
|                                  | > regions (e.g., RIR for Canada  |
|                                  | > and the                        |
|                                  | >                                |
|                                  | > United States: American        |
|                                  | > Registry for Internet Numbers  |
|                                  | > ARIN)                          |
+----------------------------------+----------------------------------+
| World Wide Web Consortium (W3C)  | > Develops standards,            |
|                                  | > guidelines, and software for   |
|                                  | > the                            |
|                                  | >                                |
|                                  | > WWW (e.g., Hypertext Markup    |
|                                  | > Language, Extensible           |
|                                  | >                                |
|                                  | > Markup Language, Cascading     |
|                                  | > Style Sheets, and SOAP)        |
+----------------------------------+----------------------------------+

4.3 The Internet Protocol
=========================

4.3.1 Internet Protocol Suite
-----------------------------

The Internet Protocol Suite consists of a set of protocols enabling
communication between network nodes both on the Internet and over other
computer networks (Baker 2009). It is also known as the TCP/IP protocol
suite (or in short, TCP/IP) after two of its most important protocols:
TCP and IP. TCP/IP provides end-to-end data communication over
heterogeneous physical networks. More specifically, the protocol suite
defines how data should be packaged, addressed, sent, routed, and
received. The IETF maintains the technical specifications of many of
TCP/IP's constituent protocols.

The TCP/IP protocol suite's independence from specific hardware and
software platforms is one of its essential qualities. As long as
hardware and software layers are capable of transmitting and receiving
data via a computer network, TCP/IP can be used to establish
communication between the nodes on that network. The platform
independence also facilitates communication between nodes on different
interconnected networks, which, given the Internet's composite network
architecture, is a highly important feature for Internet communication.
Another key TCP/IP quality is its robustness. Owing to the Internet's
military origins, one of the fundamental requirements for its protocols
was their ability to continue operating even if large parts of the
network suddenly failed. TCP/IP was therefore designed with builtin
failure recovery mechanisms to provide reliable end-to-end communication
even under adverse conditions. For instance, if data is (partially) lost
during transmission,

TCP/IP automatically resends the affected data (parts), but not
necessarily taking the same network route on which the original data
transmission went missing.

### Internet Protocol Suite

> The Internet protocol suite is a set of protocols that enables
> Internet communication by specifying data transmission, addressing,
> and routing (Baker 2009).

TCP/IP is hierarchically structured into four layers stacked on top of
one another (i.e., a protocol stack), namely: the (1) data-link layer,
(2) network layer, (3) transport layer, and (4) application layer (IETF
1989b, a). As depicted in Fig. 4.3, each of the four layers comprises
different protocols. The upper layers of the protocol suite are
logically closer to the software applications with which users interact
(e.g., Internet browser), and the lower layers are closer to the
physical networking hardware. Communication between the layers is
established by standardized interfaces between adjacent layers, which
hide the actual implementation of a layer's functionality. Each layer
offers services to the layers immediately above and uses the services of
the layer directly underneath. This strict separation creates
flexibility and greater independence from the services' implementation
in terms of both hardware and software. How these services are
implemented (i.e., which protocols are used), do not concern the layers
using them. This means that, on the one hand, layers at the top of
TCP/IP (i.e., application and transport layer) do not know how the
networking hardware handles individual bits of a data transmission. On
the other hand, the lower layers (i.e., network and data-link layer)
distinguish between the different data formats and protocols that
particular applications require. The four abstraction layers' purpose
and scope are subsequently described in detail.

The application layer provides applications with standardized interfaces
that allow them to send data to other applications or receive data from
them via a network. This allows different applications to communicate
with one another as long as they use the same application layer
protocols. Since the application layer protocols are very near the
actual applications, they support particular operational scenarios
instead of general networking functions. These types of protocols
therefore use the networking services that the underlying lower layers
offer, specifically the transport layer. The application layer protocols
regard the protocol layers below them as black boxes offering a stable
network connection for communication between applications, but also do
not affect the layers below. This means that, for instance, network
devices operating on lower-level protocols, like routers and switches,
do not generally examine the encapsulated data transmissions. Instead,
these devices are more concerned with relaying them. Consequently, all
applicationnear protocols can be found on the application layer,
including the HTTP, File Transfer Protocol (FTP), Post Office Protocol 3
(POP3), Simple Mail Transfer Protocol (SMTP), and Simple Network
Management Protocol (SNMP).

The transport layer is responsible for the correct transfer of data
between network nodes, independent of their application, specific data
structures, and underlying network (Hunt 2002). At this layer, the most
frequently used protocol is the TCP, whose primary function is providing
connection-oriented, reliable data delivery. The TCP ensures that, for
instance, data arrive in the order they were sent, that they arrive
correctly, that duplicate data are discarded, and that data lost in
transit are resent. In order to do so, the TCP establishes a
bidirectional connection over which the sending node transmits data to
the receiving node, which confirms its receipt with messages that
acknowledge receipt of the data. The TCP is therefore well suited for
cases where data integrity is important. However, this level of
integrity comes at the cost of efficiency due to the decreased
throughput. If throughput is more important than the data integrity, an
alternative transport layer protocol, the UDP, can be used. As a
connectionless protocol, the UDP neither checks that a data transmission
actually arrived at the receiving node, nor that such a node even
exists. The UDP also doesn't provide any error-recovery mechanisms,
because, for example, corrupted or lost data transmissions are not
resent. By combining connectionless data transmissions and no
error-recovery, the UDP allows for transmitting data at far lower
overhead costs and less communication delay between the hosts. The UDP's
use is therefore primarily in applications where large amounts of data
need to be transmitted with little delay and where the loss of a few
data bits can be tolerated, such as with video and audio streaming.
Nonetheless, applications utilizing the UDP might, if required, also
implement integrity mechanisms on the application protocol level.

The network layer (or Internet layer) is responsible for transporting
data between the right nodes within a network or across multiple
networks. The network layer has two important functions, namely node
addressing and data routing. To this end, the IP, which is the most
important protocol on this layer, specifies an addressing method that
unambiguously identifies a data transmission's sending and receiving
node: the IP address. As will be explained in detail in section 4.3.2,
IP addresses are numerical labels uniquely assigned to each node within
a network. Based on this addressing system, the IP also provides routing
functions that forwards data to a specific destination in the network,
identified by its unique IP address. However, the IP is a connectionless
protocol that not only does not expect reliability from the lower layers
(e.g., data-link layer), but also does not itself provide mechanisms
contributing to reliable data delivery, like error recovery. If
required, a higher-level protocol, like the TCP, needs to provide these
functions. Other network layer protocols are the Internet Group
Management Protocol (IGMP), Internet Control Message Protocol (ICMP),
Address Resolution Protocol (ARP), and Reverse Address Resolution
Protocol (RARP).

The data-link layer (also network interface layer or physical layer)
provides an interface to the actual physical networking hardware that
links two or more distributed nodes. This interface allows for sending
or receiving data transmissions to or from a data-link interface of a
different network node on the same network segment (link). The data-link
layer represents the least abstract specification of the interactions
with the hardware components. However, since TCP/IP is designed to be
independent of specific hardware implementations (i.e., can be
implemented regardless of the underlying network technology), the
data-link layer does not decree the use of particular protocols.
Instead, the data-link layer provides a standardize, but flexible,
interface for accessing such protocols, which, for instance, describe
the structure of the underlying network, or specify the interfaces that
allow for forwarding a data transmission over wired or wireless
communication technology to a neighboring network node. The following
protocols are common on this layer: IEEE 802.2, IEEE 802.11, Ethernet,
and Fiber Distributed Data Interface (FDDI).

To illustrate the individual layers' collaboration, Fig. 4.4 shows a
simplified process of retrieving a webpage from a Web server using
TCP/IP. In the example, a user opens the webpage with the URI
[http://example.com/products.html,](http://example.com/products.html)
or, in other words, the user uses a Web browser application to
communicate with a Web server. To do so, the user typed the URI into the
browser application, which runs on the application layer. When the enter
key is pressed, the browser program sends a message to the transport
layer "Get:
[example.com/products.html.](http://example.com/products.html)" At this
layer, the TCP adds information to the message, including the network
port specifying the service provided by the receiving node for which the
transmission is meant (e.g., port 80 on a Web server) and an error
checksum that allows for checking the message's integrity (i.e., that
its content has remained unchanged) at its destination. The TCP then
passes the message plus the extra information to the network layer where
the IP adds information required for delivery to the specific
destination node, including the IP addresses of the source and
destination. The TCP had determined the destination IP address earlier
by looking up the domain name address (see DNS later), [example.
com](http://example.com/) (see section 4.3.3). The data transmission is
then sent to the Web server via the Internet by utilizing the network
hardware to which the data-link layer at the bottom of the TCP/IP stack
provides an interface. At the receiving end (the server), the data
transmission crosses the server's protocol stack, but in reverse order,
by starting at the data-link layer. Once the message reaches the
application layer, the server software identifies the requested HTML
document products.html and prepares a response message that includes the
document. The response message follows the above described path back to
the user's browser program, which will display the HTML file.

User Web server

Fig. 4.4 TCP/IP Transmission Example

4.3.2 IP Addresses
------------------

As described in the previous section, TCP/IP enables communication
between the hosts located on the same network, or on different
interconnected networks. In order to ensure that the data can be routed
to the target host, each endpoint requires a unique address, called the
IP address (Stevenson and Waite 2011). RIRs assign IP addresses
centrally, but are in turn supervised by the ICANN to ensure that these
addresses are unique throughout the Internet. Currently, two different
versions of the IP are in use: IPv4 and IPv6. The IP version 4 (IPv4)
had its first large-scale application in 1983 as part of the ARPANET. An
IPv4 address is a 32-bit-long binary number, allowing for specifying
2^32^ (4,294,967,296) unique addresses. Owing to the Internet's rapid
growth, this pool of available addresses soon became too small,
prompting the IETF to increase the address space in 1995 by evolving
IPv6 into the IP version 6 (IPv6) (Deering and Hinden 1995, 1998, 2017).
IPv6 increased the address size to 128 bits, which provides up to 2^128^
(approximately 3.403 10^38^) addresses, which are deemed ample for the
foreseeable future. Currently, both IP versions are used in parallel.
Beside other technical changes, IPv6's extension of the address space
also resulted in a different address format, as will be shown in the
remainder of this section.

### IP Address

> An IP address is a group of binary numbers uniquely identifying a node
> within a network that uses the Internet Protocol (Stevenson and Waite
> 2011).

As depicted in Fig. 4.5, IPv4 addresses consist of four 8-bit-long
blocks adding up to 32 bits. In order to increase their readability,
IPv4 addresses are often split into four 1-byte-long segments (i.e.,
octets) converted into corresponding decimal numbers between 0 and 255
and separated by dots. An IPv4 address can also not only identify a
particular node on the Internet, but also the network to which it is
directly connected. To this end, an IPv4 address can be logically split
into two segments: a network identifier and a host identifier. The
network identifier, which identifies a node's network, can be one to
three octets long, depending on the size of the network. The network
identifier segment always starts from the left. The remaining segment of
the network identifier specifies the node within the network (i.e., the
host identifier). A subnet mask can be used to specify where an IP
address's network identifier ends and the host identifier starts. The
subnet mask is the length (number of bits) of the network identifier
segment (i.e., the prefix length). This number, preceded by a slash, is
appended at the end of an IPv4 address. An example of an IPv4 address
whose first 24 bits (three octets) describe its subnet:
192.168.35.22/24. The remaining 8 bits (one octet) can be used within
the network to address a maximum of 2^8^ (i.e., 255) unique nodes.

Owing to IPv6 addresses' quadruple length compared to IPv4, their 128
bits of are normally depicted as a group of eight 16-bit hexadecimal
number blocks (i.e., hextets) separated by colons. Each hextet consists
of four hexadecimal digits (bits) representing 16 binary digits, which
halves the number of required blocks compared to the decimal notation. A
typical IPv6 address:

3ffe:0db8:85a3:0000:0000:8a2e:0370:67cf. IPv6 addresses can be further
simplified by omitting the leading zeroes within a group, meaning that
'0370' can be shortened to '370,' but not to '37.' Two or more
consecutive groups of all zeros can be replaced by two colons (::), as
depicted in Fig. 4.5. When the address is expanded to its full 128-bit
length, the double colon is replaced with groups of zeros until the
address is again made up of 8 groups. However, if an address were to
have multiple double colons, it would be impossible to determine where
to add a specific number of groups to restore the address's original
representation. Consequently, a valid IPv6 address is only allowed to
contain a double colon once. In all other cases, a group must retain at
least one hexadecimal digit to prevent ambiguities (Hinden and Deering
2006). By combining all the shortening rules, the above example address
can also be written as: 3ffe:db8:85a3::8a2e:370:67cf. Like IPv4, an IPv6
address can be separated into a network and host identifier by using a
subnet mask that specifies a prefix length by using the above described
slash notation. The most common prefixes used with IPv6 are multiples of
four. For instance, the IETF defines /64 as a standard size for an IPv6
subnet, which allows for assigning 2^64^ unique addresses within the
network. A /56 subnet would allow for 256 subnets of a / 64 subnet size,
and so on.

> ![](media/image5.png){width="4.576666666666667in"
> height="1.7733333333333334in"}

4.3.3 Domain Name System
------------------------

While IP addresses are an effective approach to communicate with a
specific host, they are neither easy to memorize nor descriptive in
terms of the network resource to which they are assigned. They are
especially not practical for user-focused Internet services like email
or the WWW. In 1983, the IETF therefore proposed the Domain Name System
(DNS), which became one of the essential components of today's Internet
infrastructure (Mockapetris 1983a, b). DNS is a hierarchically
structured, decentralized set of databases that associates domain names
with a specific Internet resource or with collections thereof, such as
computers, users, networks, and services. The DNS's most important
purpose is to translate memorable text-based domain names to numerical
IP addresses, a process called DNS look-up. The DNS allows Internet
users to visit a website by typing in the domain name rather than its IP
address. For instance, the domain name [google.com](http://google.com/)
in the address bar of a Web browser or Google's Web server IP address
216.58.213.174 provide access to the website of Google's Web search
engine. The DNS also simplifies email by translating the domain name
that follows the @ symbol into the respective mail server's IP address.

### Domain Name System (DNS)

> The Domain Name System (DNS) is a hierarchically structured,
> distributed set of databases that maps IP addresses to corresponding
> domain names (Chandramouli and Rose 2006).

A domain name comprises one or more parts, called labels, joined by
dots. As depicted in Fig. 4.6, these labels are organized hierarchically
following the DNS's tree-like structure. The highest level of this
hierarchy (the root) has no DNS name. The top-level domains, including
generic top-level domains, such as com, info, net, edu, and org, or
country code top-level domains, like de, fr, or ca, are specified
directly below the root. The second-level domains, which organizations
and individuals (e.g., springer, example, google, amazon) can reserve,
lie underneath the top-level domains. Finally, a domain name may specify
a third-level domain, sometimes referred to as a subdomain or host name.
Third-level domains are not mandatory and are generally used to specify
a certain node inside an organization. The most common third-level
domain is www, which usually links to a Web server providing WWW
services. Each level adds a label to the domain name, which descends
from the right to the left. For example, the domain name [www.example.
com](http://www.example.com/) comprises the com top-level domain, the
second-level domain example, and the subdomain www.

Fig. 4.6 DNS Domain Hierarchy

The DNS itself is basically a distributed network of individual DNS
severs managing domain names and their associated records, which
specifically include the aforementioned mapping between the domain names
and IP addresses. These records are kept in DNS translation tables
distributed to and stored on numerous DNS servers around the world. For
efficiency's sake, most of these DNS servers do not keep a complete
replication of the entire DNS translation table. Instead, most of these
servers are assigned a specific domain zone that correspond to the DNS
domain hierarchy. In addition, DNS severs have some knowledge of the DNS
servers below and above their domain level, which allows them to refer
incoming look-up request to an appropriate server. As exemplified in
Fig. 4.7, the DNS lookup process involves requests to multiple DNS
servers on the different domain hierarchy levels (top-down) in order to
translate a domain name into an IP address. When a user wants to visit a
website by using its domain name, the browser will send a request to a
known DNS server that the user's ISP often maintains. If the DNS server
already knows the domain name, it will provide the relevant DNS record
directly. If the DNS server does not keep the requested domain name's
record, it will send the request to the DNS server responsible for the
relevant top-level domain. This top-level DNS server knows the IP
addresses of all second-level DNS servers directly below it in the
hierarchy and will again refer the requesting DNS server down to
relevant second-level DNS server. This process continues down the DNS
hierarchy until either the record for the particular domain name is
found or the process fails. A DNS lookup is declared failed if, during
this process, no suitable lower-level DNS server is found, or the
process exceeds a specified time limit.

Since the DNS lookup process creates additional overhead communication
costs and longer response delays when requesting resources on the
Internet, ISPs cache requested DNS records for a certain time. Once a
domain name's record is cached on an ISP's DNS server, this serves
answers all similar requests directly, instead of first undertaking a
DNS lookup starting with the DNS root layer. However, because domain
records are not static, their mapping to IP addresses can change, in
which case cached records will point to the wrong or a non-existent
server. Hence, DNS caches are frequently updated.

> ![](media/image6.png){width="4.569416010498688in"
> height="3.594153543307087in"}

Fig. 4.7 Example DNS Lookup

4.3.4 IP-Routing and Packet Forwarding
--------------------------------------

In order to understand how data find their way through the Internet to
their destination, it is important to first define what is transmitted.
Up to this point in this chapter, any data sent via the Internet has
been treated as a single coherent message. However, this is not actually
how data are transmitted. TCP/IP uses a method called packet switching,
which means that data are not transmitted as single units, but are
divided into smaller blocks that are sent separately. These data blocks,
called IP packets, are reassembled once they reach their destination.
The Maximum Transmission Unit (MTU) size is one of the main reasons for
using packet switching. The MTU defines the maximum data size of a
packet sent or received in a single network transaction. The underlying
network infrastructure, which makes a trade-off between different
factors, such as efficiency and reliability, determines the MTU. For
example, larger units allow for sending the same amount of data, but in
fewer packets, thus increasing the efficiency by reducing the cumulative
overhead costs. However, if a packet is corrupted in transit and has to
be resent, a larger data unit will reduce the efficiency by increasing
the overall amount of network traffic. A common MTU value of 1,500 bytes
is common for Ethernet-based networks (Hornig 1984). This means, for
example, that when downloading a document of 10 MB, the file cannot be
transmitted as a single data unit, as the package exceeds the MTU
limitation of the underlying transmission system.

### Packet Switching

> Packet switching describes a switching and transmission technology
> which splits complete messages into smaller packets. These packets can
> be transmitted via a network's different lines and the receiving host
> re-assembles them into the original message (Jordana 2002).

While a packet's specific content varies in respect of the applied
protocols, all packets generally consist of two parts: a header and a
payload. The header portion stores overhead information on the packet's
content (e.g., the encoding style), the underlying protocol, and
transmission-related data (e.g., the sending and receiving nodes' IP
addresses and a packet's sequence number that specifies its reassemble
order once all of a transmission's packets have arrived at their
destination). The payload comprises the actual data block being carried,
which is the message content or a part of it. Like an onion, an IP
packet usually comprises multiple layers, one for each protocol used for
a particular connection, each of which has its own header. As depicted
in Fig. 4.8, each layer has a payload and a header containing protocol
information relevant for the layer. The next outer layer treats the
entire layer to be encapsulated as payload (data) and adds its own
header. In other words, each layer considers the packet it receives from
the layer above it as one coherent data block. This process of attaching
new headers to existing data is called encapsulation and, at the
packet's destination, the protocol stack reverses this process in the
same order.

Fig. 4.8 IP Packet Encapsulation Process

Once the packets are prepared, the remainder of the packet switching
process mainly consists primarily of routing them via the Internet and
to their relevant destination. This process actually comprises two
tasks: routing (i.e., choosing the path for a packet) and packet
forwarding (i.e., the delivery of packets to another node). Specially
configured systems, which can be either routers or switches, usually
handle both tasks. A router acts as a gateway between two or more
networks by connecting them physically and handling the packet exchange
between them (Grance et al. 2008), which makes routers particularly
important for the Internet's multi-network architecture. Switches serve
a similar function, but instead of connecting different networks with
one another, they interconnect nodes within the same network. For
clarity's sake, the following explanations do not differentiate between
routers and switches.

### Router

> On a network, a router is a device that determines the best path for
> forwarding a data packet toward its destination. A router is connected
> to at least two networks and is located at the gateway where one
> network meets another (Grance et al. 2008).

When receiving a packet, routers first perform basic error check
routines. This includes, for instance, validating that a packet's
checksum matches its content, which could indicate that its header or
payload were modified in transit (Information Sciences Institute 1981).
Routers also check whether a packet's time to live (TTL) limit has been
exceeded. TTL limits a packet's lifespan by either defining a maximum
number of transfers between routers, or a timespan to prevent a packet
from circulating indefinitely. If the router cannot fix the packet, it
is discarded and an error message sent to its sender. Depending on the
type of error and the packet's history, the sender's TCP implementation
may decide to resend the discarded packet or terminate the entire
transmission.

If the packet is without errors, the router then determines its next
routing target, also called a hop, on its way to the destination address
specified in its header. This routing decision is made with the help of
routing protocols that apply different algorithms to identify the best
path to take, to facilitate establishing a network's structure, and to
gather information about neighboring routers from the surrounding
environment. Routing protocols also specify the handling of packets
(e.g., error checking) and the forwarding process.

There are two major routing protocol archetypes, namely distance vector
routing and link state routing. Distance vector routing often applies
the Bellman--Ford and Ford--Fulkerson algorithms to calculate a graph
comprising all of the available routes within or between networks. Each
node determines the travelling cost to each immediate neighbor (Ford and
Fulkerson 1956; Bellman 1958), because, in the routing context, these
costs usually refer to metrics like the throughput, delay, transit fees,
and reliability (Baumann et al. 2007). This information is gathered in
respect of each node and used to build a distance table, which allows
for identifying the best path (i.e., the least costly) in support of a
routing decision. The Interior Gateway Routing Protocol (IGRP) and
Routing Information Protocol (RIP) are specific examples of distance
vector routing protocols.

Link-state routing also tries to find the path with the lowest costs,
but with a more local perspective. This means that a router based on
distance vector routing cooperates with the other nodes, allowing each
node to find the cheapest path to every other node linked directly to
it. These data are then shared by the nodes and processed by using a
standard shortest paths algorithm, such as Dijkstra\'s algorithm
(Dijkstra 1959). Contrary to distance vector routing, which looks for
the cheapest path between nodes A and C, link-state routing determines
the least-cost path in a multiple of distinct paths (e.g., A to B and B
to C). Such routing calculations are more effective, but also more
time-consuming. The Open Shortest Path First (OSPF) and the Intermediate
System to Intermediate System (IS-IS) routing protocols are examples of
protocols using link-state routing.

Owing to the large number of packets a router has to handle, it is not
practical to actually determine the best route by using complex
algorithms for each incoming packet. Routers therefore use routing
tables that store hop targets, which routing algorithms predetermined in
order to identify the best next hop within the network or between
different networks. To determine where a specific packet needs to be
forwarded, a router simply has to find a suitable hop target within its
routing table that directs the packet closer to its destined node. The
routing table entry involved in the process does not necessarily need to
be a precise match with the packet's destination IP address. A router
may also use an approximate algorithm, like Longest Prefix Match, which
identifies the closest destination based on subnetwork masks (i.e.,
longest match with the destination IP address's prefix) (Comer 2015).
Once a suitable match is found, the packet is forwarded using the
routing table information. This forwarding target is either another
router that takes the packet closer to its destination, or the actual
destination (if it is in reach of the router), which concludes the
routing process.

If no appropriate forwarding target can be identified for a packet, it
is sent on a default route with the expectation that it will find a
router that can determine an appropriate route. This default route
usually takes the packet up the ISP hierarchy (see section 4.2). The
higher the network tier, the larger the maintained routing tables' size.
Tier 1 ISPs often have the most extensive routing tables, which
therefore have the best chance of determining where a packet should be
sent. If an appropriate routing target is still not found, the packet
will be discarded at some point (e.g., when reaching its TTL limit),
which also concludes the routing process.

4.4 Content Delivery Networks

4.4 Content Delivery Networks
=============================

The reliable and fast delivery of content via the Internet is a
challenging task due to the unpredictability of users' demand, which
causes high server loads that exceed the available resources, and the
large geographical distances between the content providers (i.e.,
entities that supply digital media, like texts, videos, and pictures,
via the Internet) and the consumers across the globe. With the global
Internet traffic continuously growing, load balancing approaches have
become highly important for content providers trying to improve their
customer experience (Robinson 2017). As the name implies, load balancing
is an approach distributing the overall computational load burden (e.g.,
users requesting a website) evenly over multiple devices, ensuring that,
at any given point in time, a single hardware or software component is
not strained beyond its technical limitations. However, load balancing
is not a function implemented at the Internet's core architecture level,
as it was only designed with essential, but robust, network
functionalities in mind (Saltzer et al. 1984). The implementation of
more complex operations, like dealing with high load peaks caused by
incoming resource requests, is the responsibility of nodes connected to
the Internet.

An intuitive load balancing implementation is to build a large enough
data center to host multiple redundant content servers with an
appropriate load balancing mechanism to handle regular traffic and
exceptional demand peaks. However, centralizing all computing resources
in a single geographical location creates a single point of failure and
does little to improve performance problems caused by network issues,
large physical distances between a provider and customers, and power
outages. Owing to these drawbacks, content providers settled for a
different solution: content delivery networks (CDNs) (Pathan et al.
2008). Over the past decade, CDNs have become a vital part of the
Internet architecture and by 2022 CDNs should be handling up to 72
percent of the global Internet traffic (Cisco 2018).

> ![](media/image19.png){width="4.569972659667542in"
> height="1.5983191163604549in"}

Fig. 4.9 (Left) Single Server Distribution (right) CDN Distribution
Scheme

A CDN is a collection of network devices controlled by a common
management infrastructure aimed at delivering content (e.g., websites,
video streams, audio streams) more effectively via the Internet to
content consumers (IETF 2003). The basic principle behind a CDN is to
deliver content not from a central server, but to move it to network
locations closer to content consumers (Fig. 4.9). By reducing the
distance between the content and the consumer, CDNs decrease data
transmission latencies, the risk of connection interruptions, and
increase the transmission speed, which ultimately improves the user
experience. This is done by replicating the content on multiple content
delivery servers, also called surrogate servers, in different
geographical locations (Cooper and Tomlinson 2001). Clients' content
requests are automatically routed to the surrogate servers, a process
often invisible to the requesting clients.

Content Delivery Network (CDN)
------------------------------

> Content Delivery Network (CDN) is a type of content network in which
> the content network elements are arranged for more effective delivery
> of content to clients. A CDN usually comprises a request-routing
> system, surrogates, a distribution system, and an accounting system
> (IETF 2003).

A content provider (e.g., Netflix) either operates a CDN directly or a
dedicated service provider acting on behalf of the content provider
delivers content to its consumers. The latter is more common, as
operating an own CDN with multiple points of presence in locations
geographically far apart (i.e., close to the content consumers) involves
high investment and maintenance costs (e.g., data centers, network
infrastructure, labor costs). Moreover, most content providers' core
business is the production of content, as they often have little
expertise in the management of network infrastructures. Specialized
network service providers, such as Amazon or Cloudflare, which sell CDN
as a service to various content providers, therefore often run CDNs.

As depicted in Fig. 4.10, a CDN's architecture is basically comprised of
four components, (1) a content-delivery infrastructure, (2) a
request-routing infrastructure, (3) a distribution infrastructure, and
(4) an accounting infrastructure (Hofmann and Leland 2005; Bartolini et
al. 2003). The content delivery infrastructure contains the physical
surrogate servers and the corresponding maintenance overheads. When a
client requests a single content item from a CDN (e.g., a user request
for a certain website), the request is directed to the best suited
surrogate server with a copy of the item. As depicted in Fig. 4.10, a
CDN could, for instance, operate one surrogate server per continent,
each only handling requests from users located on the that continent.

The task of steering or directing a content request from a client to the
right surrogate server is handled by the request-routing infrastructure.
The selection of the "best suited" surrogate server usually means that
the server promising the specific client the shortest delivery time with
appropriate integrity and consistency

4.4 Content Delivery Networks

will deliver the item. The shortest delivery time is therefore not
necessarily only dependent on static information, like a surrogate
server's geographic location and network connectivity. Consequently, the
request-routing infrastructure often incorporates dynamic information,
like the current network conditions and the surrogate servers'
computational load, into its decision on where to best direct user
requests.

The distribution infrastructure handles activities concerning the
content's distribution within the CDN. All content delivered through a
CDN is first published as a master copy on an origin server. A content
item's master copy is then replicated on one or more surrogate servers,
which deliver copies of the content to a specific set of users. The
distribution of the master copy to surrogate servers can either be
implemented through pre-positioning (i.e., prior to user requests) or
through on-demand fetching (i.e., in response to a user request to a
surrogate server). If a content item needs to be modified or deleted,
these changes are first applied to the master copy on the relevant
origin server and afterwards replicated on the surrogate servers.

The final component is the accounting infrastructure, which is
responsible for measuring and recording the networks' content
distribution and delivery activities. Keeping a record of these
activities is very important, especially when the CDN delivers
third-party content, since this information is used to calculate a
client's (i.e., the content provider's) service fees.

> ![](media/image20.png){width="4.573333333333333in"
> height="3.706667760279965in"}

Fig. 4.10 Exemplary Structure of a CDN Distribution Infrastructure

In the CDN infrastructures discussed above, a content provider and
content consumer are regarded as two different entities. However, this
might not always be the case. For instance, a global retail organization
can decide to build its own CDN to deliver content to its different
subsidiaries across the globe. This type of network is called a private
CDN, because its surrogate servers only serve content within the
provider's (virtual) private network, which is restricted to certain
business divisions, user groups, or persons. Depending on the
organization's size, such a private CDN can range from just a pair of
distributed caching servers to structures capable of serving thousands
of content consumers (Savitz 2012). Large public CDNs sometimes also use
private CDNs as part of their content distribution infrastructure to
deliver content to their public surrogate servers (Google 2012). Private
CDNs are most suited for organizations with specific location
requirements (i.e., the placement of surrogate servers), distribution
requirements (e.g. high bandwidth or low latency), or security
requirements, like in healthcare (Sunyaev et al. 2010; Sunyaev and Pflug
2012; Dehling and Sunyaev 2014).

A federated CDN, which is based on an infrastructure operated by
multiple content or service providers, is another CDN variation (Cisco
2011). Essentially, the participating providers pool their pre-existing
resources in a single delivery network that enables its members to
deliver their content to each node connected to the federated network.
This means, for example, that when two national CDN operators A, in
Australia, and B, in Belgium, agree to cooperate via a federated CDN
infrastructure, provider A's content is delivered to content consumers
in Belgium via B's national network, and vice versa. Content providers'
interconnection can be implemented either bilaterally or via an exchange
hub (Cisco 2011). In the former, each participating provider connects
directly with every other provider in the network. When implementing an
exchange hub, a central networking node orchestrates the content
replication and delivery on behalf of all the providers. Regardless of
the distribution approach, federated CDNs' main advantage is that
smaller content or service providers can compete with larger CDNs, like
Akamai or Limelight Networks, by reducing the operational complexity and
costs for the individual providers and giving them more control over
their content's distribution.

A peer-to-peer (P2P) CDN is a final example of an alternative CDN type.
P2P describes a distributed application architecture in which equally
privileged nodes (i.e., the peers) are directly interconnected with one
another in order to share resources (e.g., services or data) (Dougherty
et al. 2002). Unlike in the client-server architecture, in P2P networks
there is no differentiation between resource providers and consumers, as
each node fulfills both roles. The emergence of protocols, such as
BitTorrent, used for sharing files without the need for a central server
infrastructure has made P2P CDNs familiar to a wider audience of
Internet users. In a P2P CDN, the network's clients (i.e., peers), which
both provide and consume the content, either partly or completely
replace surrogate servers. A P2P CDN creates a densely connected network
with directly cross-linked Internet nodes to access the same content
items. The CDN coordinates its clients to send chunks of an item to one
another, instead of everyone sending individual requests to the same
origin server. Consequently, the more content-consuming nodes use the
network, the more effective P2P CDNs become, especially if the network
is based on protocols, such as

BitTorrent, that require its nodes to share content while accessing it.
Clients' involvement in the content delivery process can either be used
to unburden existing surrogate servers or replace them completely. While
this approach limits the content provider's control over the delivery
process, it greatly reduces the CDN's setup and operational costs (Li
2008; Stutzbach et al. 2005).

In summary, each CDN type has its own distinct strengths and suitable
application scenarios. However, all CDN approaches have enabling
providers of popular content source, of content with fluctuating request
patterns, and of a geographically distributed audience by means of a
reliable and fast service for their content consumers in common.

4.5 Emerging Internet Network Architecture
==========================================

The ongoing digitalization of today\'s society means that the demands
placed on the Internet are growing as well. The Internet is therefore
subject to continuous development and renewal. In the following,
emergent architectural concepts will be presented that reflect the
Internet network architecture's renewal process.

4.5.1 Software-Defined Networking
---------------------------------

Software-defined networking (SDN) is an architectural approach for
centralizing and simplifying computer networks' design and management by
decoupling packetforwarding activities (i.e., the data plane) from the
decision process of how and where to send packets (i.e., the control
plane) (Open Networking Foundation 2012). A similar functional
distinction was made in section 4.3.4 when describing that network
devices (routers or switches) first determine packets' optimal paths and
only then forward them to adjacent nodes. In addition to routing
decisions, the control plane is also responsible for network activities'
monitoring and the enactment of the rules that the network operator
sets, such as the traffic prioritization from or to certain nodes, or
the security policies limiting access to parts of the network, or
blocking specific packets due to their content. The different
quality-of-service levels that the network operator sells to its
customers require network devices to prioritize one customer's traffic
over another in order to provide the promised network performance - a
practical example of the abovementioned rules. The control plane is
therefore of particular importance for network operators, since it
defines the network's behavior and affects its overall performance.

A network's control plane is usually distributed across all the employed
network devices. This means that once a device is configured, it
autonomously gathers information about its surrounding network
infrastructure by communicating with neighboring devices and
subsequently makes routing decisions based on its preconfigured routing
protocols. On the one hand, this distributed control approach makes the
network more resilient due to its independence from a centralized
control system (i.e., a potential single point of failure). On the other
hand, distributing control also entails the configuration being
distributed. Network-wide configuration changes require manual
reprogramming of each individual network device, which adds to the
complexity of adapting a networks behavior to changing (application)
requirements. Given that large computer networks (e.g., ISP networks)
comprise hundreds if not thousands of networking devices by different
manufacturers with different management interfaces, updating a network's
configuration can be difficult and expensive. SDN's goal is to overcome
this challenge by consolidating the control plane in one
software-defined control system that instructs the network devices on
how to forward packets and which can be centrally administered (Benzekki
et al. 2017).

### Software Defined Networking

> Software Defined Networking (SDN) is an emerging network architecture
> in which network control is decoupled from the forwarding devices and
> is directly programmable (Open Networking Foundation 2012).

As depicted in Fig. 4.11, SDN defines three separate layers that
interact with one another through standardized application programming
interfaces (APIs). While the individual network devices located at the
data layer still handle the forwarding of packets, all the control
functions are moved from the individual hardware components to a single
software controller (i.e., the SND controller) that runs on a central
system. Consequently, the SDN controller acts as a control hub enabling
applications from the layer above to dynamically change how the
individual network devices on the data layer below handle the network
traffic. Two types of APIs establish communication between the
application, control, and data layers: southbound and northbound APIs.

The southbound APIs connect the control and infrastructure layer. In the
downward direction, the control layer sends configuration and routing
information to the physical network devices (e.g., switches and
routers). The network devices transmit operational data required for
monitoring indented the network traffic up to the control layer. One of
the API's main purposes is to control the routing of packets across
network nodes. To ensure this control, the OpenFlow protocol, introduced
in 2011, was the first standard used in southbound APIs and is currently
still the most common (Little 2012, 2013). However, several alternative
approaches, proprietary and open source, have been developed to create
hardware abstraction layers, such as Cisco Systems\' Open Network
Environment and the Nicira Network Virtualization Platform.

The northbound APIs enable communication between the SDN controller and
the software applications above that require network services to fulfill
their intended function (Subramanian and Voruganti 2016). Such
applications may utilize northbound APIs to customize the virtualized
network infrastructure to their needs, and to access the network
services that the control layer provides (Duan and Toy 2016). In
contrast to southbound APIs, there is currently no standard protocol for
northbound APIs. SND often implements northbound APIs by using RESTful
service interfaces based on the REST architectural style (see chapter
6).

Fig. 4.11 Software Defined Network Architecture (adapted from Open
Networking Foundation (2012))

One of the major advantages of SDN's separation of layers by means of
standardized APIs is that the resulting loose coupling between the three
layers enables virtualization and the dynamic allocation of network and
service functions to an arbitrary underlying physical infrastructure.
Consequently, SDN promises numerous benefits, including the physical
network infrastructure's increased scalability (up and down), as well as
the ability to monitor and adapt network resources quickly and precisely
to exactly match the application and data needs. Another practical
example of SDN benefits is the monitoring of network security. With the
help of the centralized control layer, SDN operators can detect network
anomalies caused by malicious behavior from inside or outside the
network (e.g., unauthorized access to secured network nodes) much faster
than in traditional, decentralized architectures. Once an anomaly has
been detected, the affected network components, or whole sections, can
be immediately reprogrammed to mitigate further damage (Giotis et al.
2014; Braga et al. 2010). Nonetheless, as mentioned previously, network
controls' centralization also comes at the cost of introducing a single
point of failure into the network, which may decrease its reliability
(Benzekki et al. 2017).

4.5.2 Network Functions Virtualization
--------------------------------------

The idea of increasing network infrastructures' flexibility and agility
through separation is a common theme in emerging network architecture
approaches. This is true of SDN (see section 4.5.1), which separates
control over a network and the network traffic's actual forwarding
process. However, SDN alone does not affect the coupling of the network
functions (e.g., intrusion prevention, load balancing, deep packet
inspection) and purpose-built networking hardware, such as
intrusiondetection devices, routers, and hardware firewalls.
Non-virtualized network functions are usually implemented by combining
specialized, proprietary software and hardware (ETSI 2013), which makes
deploying new functions, which new services or applications require, in
an existing network difficult. Owing to such networking devices'
specificity, they often either need a fundamental reconfiguration, or
even replacement, in order to execute new functions, which ultimately
creates high investment and operational costs and makes it more
difficult for network operators to provide dynamic networking services.

Network function virtualization (NFV) is an architectural principle that
separates network functions from the hardware on which they run by using
virtual hardware abstraction (ETSI 2018). Similar to the already common
approach of virtualizing server hardware, NFV replicates the physical
networking devices' functionality by using a software layer that can be
used on any computing hardware. The European Telecommunications
Standards Institute (ETSI), which is also responsible for the further
development of the architectural approach, specified NFV in 2012 (Chiosi
et al. 2012). As depicted in Fig. 4.12, the virtualized network
functions (VNFs) implement network functions as software components that
run on an NFV infrastructure. An NFV infrastructure comprises the
physical hardware devices with computational, data storage and
networking capabilities, which are assumed to be general purpose servers
and storage devices (i.e., commercial off-the-shelf hardware). An
additional virtualization layer, or hypervisor, decouples these
capabilities from the hardware devices in order to provide a dynamic
infrastructure that allows for evolving and scaling the VNFs and the
hardware resources independently from one another. To control both the
VNFs and the virtual infrastructure, NFV implements a management and
orchestration system, which handles, for instance, the virtual and
physical resources' coordination, the NFV infrastructure's monitoring,
and the VNFs' deployment in the virtual infrastructure.

### Network Function Virtualization

> Network Functions Virtualization (NFV) describes the architectural
> principle of separating network functions (i.e., functional blocks
> within a network infrastructure that have well-defined external
> interfaces and well-defined functional behavior) from the hardware on
> which they run by using virtual hardware abstraction (ETSI 2018).

As mentioned at the outset, NFV and SDN are related approaches, as they
both decouple logical functionality and physical devices, which is why
the two approaches can be combined to create a potentially greater value
for the network operator. However, NFV can be implemented without SDN
using the established server virtualization techniques used in many data
centers. Vice versa, SDN does not necessarily require NFV approaches to
separate the control and the data-forwarding planes. Nonetheless, NFV
can facilitate SDN by delivering the infrastructure that allows the SDN
to be implemented as a networking function.

NFV and SDN emphasize the utilizing off-the-shelf hardware and providing
dynamic networking services (Chiosi et al. 2012). It is therefore not
surprising that the benefits associated with the NFV approach are also
closely aligned with SDN. NFV does not require purpose-built network
hardware, since virtual networking devices can perform their tasks on
basically any general-purpose computing device, such as commercially
available workstations or servers. This often translates into large cost
savings, because specialized hardware solutions are often produced in
smaller quantities, which in turn leads to high prices per unit.
However, network operators can easily repurpose existing computing
resources for use in an NFV infrastructure, therefore also reducing the
risks of the costly over- or underprovisioning of networking resources.
The virtualization of networking devices can be added or subtracted when
required, which means NFV also increases a network's agility and its
ability to adapt to shifting business requirements. Network operators
can, for instance, tentatively test new configurations or services to
incrementally meet their customers' or their organization's current
needs without having to invest in new hardware components.

Fig. 4.12 High-level Architecture for Network Function Virtualization
(adapted from ETSI

(2013))

4.5.3 Overlay Networks
----------------------

Overlay networks, also referred to as SDN overlays, are virtual networks
of nodes, and the logical connections between them that run on an
existing underlying network infrastructure (Bagad and Dhotre 2009).
Overlay networks, which are somewhat similar to SDN, create an
additional software layer that abstracts an underlying network's
functionality. This software layer can then be customized to provide
specialized services which are not available on the underlying network,
or would require substantial reconfiguration of the network design
(Malatras 2015). Overlay networks are therefore particularly useful when
the underlying network cannot be easily customized to enable individual
service offerings, which certainly applies to the Internet. It is not
surprising that many well-known Internet services can be classified as
overlay networks running on top of the public Internet. These services
include, for instance, virtual private networks (VPN), peer-to-peer file
sharing, and voice over IP (e.g., Skype). In the past, the Internet
itself was an overlay network. As described at the beginning of the
chapter, the Internet started as a research network interconnecting
computer nodes via preexisting public telephone networks; in other
words, the Internet overlaid the physical telephone infrastructure
(Huang and Wu 2018). Currently it is the other way around, with
telephone services turning into overlay networks on top of the Internet
by switching to digital telephony solutions based on voice over IP
(VoIP) technology.

### Overlay Network

> An overlay network is a virtual network of nodes and logical links
> built on top of an existing network in order to implement a network
> service not available in the existing network (Bagad and Dhotre 2009).

From a technical perspective, an overlay network uses software to create
an abstract network layer overlying a physical network. This abstraction
layer allows for defining overlay nodes on top of existing network nodes
and the virtual connections between them. These overlay nodes need not
correspond to the physical links between the underlying network nodes
(see Fig. 4.13). The two or more involved nodes using the same software
application layer that implements the extended network functionalities
(e.g., encryption) create a virtual connection between themselves using
a common overlay communication protocols, also known as tunnel protocols
(Babay et al. 2017). These tunnel protocols basically encapsulate
traffic inside IP packets, decoupling this traffic from the standardized
TCP/IP processing logic, which in turn creates a virtual tunnel running
through the network.

Software-defined virtual connections provide high customizability by
allowing the implementing of purpose-built protocols that provide
functionalities that the Internet does not support natively (without
additional components), while still benefiting from its well established
and scalable infrastructure. Without overlay networks, developers of
innovative services might be forced to either create new purpose-build
networks or extend the current Internet infrastructure to natively
(without additional components) support the functionalities required for
their innovative applications (Babay et al. 2017). In comparison to
these expensive and timeconsuming endeavors, creating an overlay network
is often a more efficient approach to adapting a network's
infrastructure.

However, there are also drawbacks that need to be considered when
deciding to deploy or utilize an overlay network (Galán-Jiménez and
Gazo-Cervero 2011; Sitaraman et al. 2014). In particular, the overlay
abstraction layers, often stacked in multiples, add more protocols on
top of the underlying network's existing protocol stack (e.g., TCP/IP),
thereby increasing the performance overhead costs and the communication
complexity. Consequently, data exchange via an overlay network might
require more network bandwidth due to the additional steps increasing
the packet overhead costs and processing power when (de-) encapsulating
the packets. Furthermore, the additional network complexity as a result
of the multilayer structure makes it more difficult to track down the
root causes of performance or availability issues, which might be
located at any of the virtual or physical networking layers
(Galán-Jiménez and Gazo-Cervero 2011).

> ![](media/image21.png){width="4.569417104111986in"
> height="2.2111253280839893in"}

Fig. 4.13 Simplified Architecture of an Overlay Network

4.5.4 Information-Centric Networking
------------------------------------

Today's Internet architecture, which is based on TCP/IP, can be
described as location-centric. Knowledge, in the form of an IP-address
or domain name, is required about information's and services' location
before such information and services can be accessed. It is not
difficult to imagine that it would be far more convenient for Internet
users to retrieve the desired information directly, instead of having to
first search for the right website hosting the information. Further,
this tight bond between the data/services and the location makes
maintaining discoverability more difficult when the location is changed,
for instance, to decrease the physical distance to the users, increase
the retrieval speed, and decrease the network traffic. However, this
would require a paradigm shift away from TCP/IP and toward approaches
that allow information and service discovery regardless of the
distribution channel.

Such approaches are summarized under an architectural concept called
information-centric networking (ICN). In ICN, which data are being
communicated becomes more important than who is communicating them
(Yaqub et al. 2016). Consequently, ICN probably envisions the most
fundamental redesign of the existing Internet architecture compared to
the other approaches described in this subchapter. In ICN, data become
independent from their location, intended application, form of storage,
and means of transportation, which enables innovative ways of data
discovery and caching (Kutscher et al. 2016).

ICN can be implemented on different layers of the TCP/IP protocol stack.
On the application and transport layers, ICN implementations may offer
resource-naming overlays, location-independent content storage, and
native content caching enabled by globally unique resource identifiers.
On the network and data-link layers, ICN could act as a packet-level
redesign of the current IP-based addressing of nodes, packet routing,
and forwarding principles. One example of the latter is the
contentcentric networking (CCN) architecture (Jacobson et al. 2009),
whose basic idea is that a user can broadcast an information need in the
form of an interest packet specifying the sought after content's unique
name. Depending on the specific CCN implementation, the content name may
follow a hierarchical URI-based naming scheme. As depicted in Fig. 4.14,
the interest packet is routed to a suitable content source, or cache,
that can deliver the specified content interest (e.g., guided by a
longest prefix match approach based on the URI). Each time, the interest
passes a router, a record is created and stored in the router's pending
interest table (PIT). These PIT records allow for tracing the packet's
network path. Once a match is found between the proclaimed interest and
the content object, the content object is enveloped in one or more
content packets and routed back to the content consumer. The packets
then take the reverse of the interest packet's path by following the
previously created PIT records. With this approach, routing to and
retrieval of content objects are not dependent on the object being held
at a fixed location. This allows for a native implementation of content
object caches at every CCN node, which drastically increases interest
packets' chance of encountering a cached replica of the sought-after
content object before reaching the content's origin node.

> ![](media/image23.png){width="4.569972659667542in"
> height="3.6283202099737535in"}
>
> Fig. 4.14 Content-Centric Networking (CCN) architecture (adapted from
> Yaqub et al. (2016))

Another example of an ICN approach is the Publish-Subscribe paradigm,
which consists of three basic elements: (1) information publishers, (2)
information subscribers, and (3) a network of rendezvous points (RP)
where the information exchange between the publisher and the subscriber
takes place. The PublishSubscribe Internet Routing Paradigm (PSIRP) was
one of the early models, which envisioned a public subscription
architecture (Tarkoma et al. 2009). In this paradigm, information items
containing a data set and metadata are the architecture's core
component, and are labelled and organized within scopes (Tarkoma et al.
2009). Scopes may denote a physical structure, like a corporate network,
or represent a logical equivalent of the topology concept. An
information item's location can therefore be specified by means of a
rendezvous identifier (RId) and scope identifier (SId). The RId is the
information item's unique identifier within a scope, whereas the SId
denotes the scope in which an information item belongs (Fotiou et al.
2010). Scopes can also be nested within one another, which allows for
creating flexible structures and increases the control over information
dissemination, because scopes are responsible for an information item's
policy and boundary enforcement (Tarkoma et al. 2009). To publish an
information item, the publisher needs to know the SId of the scope in
which it wants to publish its information. The information item is
subsequently forwarded to the specific rendezvous point, which is hosted
on a node in the network responsible for managing the scope (Tarkoma et
al. 2009). To obtain the information, the subscriber issues a
subscription message consisting of the SId and RId, which are then
mapped to the required information item's forwarding identifier (FId).
The rendezvous function is responsible for finding a suitable data
delivery path in the network and linking it with the FId. The
intermediate routers use the FId to select the interface for forwarding
the information. This label-based forwarding releases the router from
maintaining the forwarding states and increases the network's
scalability. Consequently, PSIRP can be implemented without relying on
the IP protocol (Tarkoma et al. 2009; Fotiou et al. 2010).

ICN is an abstract idea for redesigning information retrieval with many
potential implementation approaches, as described above. Despite these
implementation approaches' differences, their common goal is to improve
the performance and user experience of accessing information via the
Internet and, at the same time, decreasing the Internet infrastructure's
load (ICNRG 2018). Providing access to content and services by means of
their names instead of their location, creates new and innovative
caching approaches. Once information can be easily retrieved without
having to know where it is stored, it becomes easier to implement
extensive content caching and ICN-like infrastructures to shorten the
paths between content providers and content consumers, which, in turn,
increases the network performance and decreases the network traffic.
Despite these benefits, ICN is not likely to replace location-centric
network technologies in the near future, especially not the Internet
whose success is rooted in agreed upon technological standards at its
core architectural level. However, to obtain the previously mentioned
benefits, ICN could be implemented as an overlay on top of the existing
Internet architecture, which will then become more relevant for future
content delivery and could even replace existing approaches like CDN
(Kutscher et al. 2016).

Summary
=======

With its roots in the 1950s as a U.S. military initiative, today's
Internet architecture has come a long way. Some of the important
milestones along this way were: the construction of the ARPANET (1969),
the development of fundamental communication protocols like TCP/IP
(1974) and HTTP (1989), the creation of the World Wide Web (1989), and
the opening of the Internet to commercial service providers (1995).
Since then, the Internet has become one of the most influential
inventions in the history of mankind. Within 60 years it went from being
a vague idea to an infrastructure used by more than four billion people
around the globe and continues to grow and evolve through novel ideas,
services, and architectures.

From an architectural perspective, the Internet can be described as a
massive network of computer networks interconnect via the global
Internet backbone. Commercial Internet Service Providers (ISPs) manage
each subnetwork's operation and the interconnections between these
networks. Depending on the managed network size, ISPs are classified
into three tiers: tier 1 ISP (large-sized networks, national

Summary

scope, peer with other tier 1 ISP), tier 2 ISP (medium-sized networks,
regional scope, peer with tier 2 ISP and purchase transit from tier 1
ISP), and tier 3 ISPs (small-sized networks, local scope, purchase
transit from tier 1 and tier 2 ISPs). To establish communication between
two endpoints via the Internet, up to three ISP levels must work
together.

Non-profit organizations largely carry out the Internet's
standardization and administration. These efforts include the
standardization and further development of the Internet infrastructure
(e.g., Internet Engineering Task Force), the administration and
registration of Internet Protocol (IP) addresses for the different
Internet regions (e.g., American Registry for Internet Numbers), the
management of the domain name system (i.e., Internet Corporation for
Assigned Names and Numbers), and the development and standardization of
Web technologies (e.g., World Wide Web Consortium).

The Internet protocol suite, which specifies, for instance, how data are
transmitted, packaged, addressed, routed, and received, is one of the
cornerstones of the Internet architecture. This suite consists of four
layers: the application layer, transport layer, network layer, and
data-link layer. Each layer defines protocols, like the Transmission
Control Protocol (TCP, transport layer) and Internet Protocol (IP,
network layer), which, combined, provide end-to-end data communication
via heterogeneous physical networks. This communication is based on a
method called packet switching, which splits data transmissions into
smaller data packets that are individually routed through the Internet
to their recipient. To find the right recipient, each computer connected
to the Internet is assigned a unique IP address, which consist of a
32-bit (IPv4) or 128-bit (IPv6) number. Devices called routers forward
packets through the Internet based on their IP address. Each router
sends a packet to a neighboring router closer to the packet's recipient
until it reaches a router directly connected to a computer with a
matching destination IP address. Since IP addresses are difficult to
remember, they can be assigned text-based domain names. The Domain Name
System (DNS) handles the process of translating the domain name into the
associated IP address, which is called the DNS lookup.

When providers distribute content (e.g., websites, videos, or pictures)
to their customers, they currently often employ Content Delivery
Networks (CDNs). A CDN usually consists of a collection of surrogate
servers that holds a copy of the content to be distributed and is
strategically placed to minimize the physical distance between the
content consumers and the surrogate server, which decreases the data
transmission latencies, the risk of connection interruptions, and the
transmission speed, thus ultimately improving the user experience.

Concluding this chapter, four emerging Internet network architectures
were presented: software-defined networking (SDN), network function
virtualization (NFV), overlay networks, and information centric
networking (ICN). SDN centralizes control over a network by separating
network packets' forwarding process (the data plane), routing process
(the control plane), and applications utilizing network functions. This
separation enables the network control to be directly programmed and the
underlying infrastructure to be abstracted for applications and network
services like server virtualization, cloud computing, and mobile
networks.

Northbound and southbound APIs interconnect the separated planes. NFV
replicates physical networking devices' (e.g., switches, load balancers,
or routers) functionality by means of software components. Since these
virtualized devices can run on any general-purpose hardware, NFV reduces
costs by making specialized and expensive devices obsolete. NFV also
makes network infrastructures more flexible, as it reduces the risks of
networking resources' costly over- or under-provisioning. Overlay
networks allow for operating discrete virtualized network layers on top
of a physical network, thereby enabling new services or functions which
would otherwise have required the network design's reconfiguration. This
is of particular interest when the underlying network cannot be easily
customized, which certainly applies to the Internet. Finally, ICN
architectures shift the perspective from communication between two
machines (location-centric) to content or service offerings identified
by their names (content-centric). This paradigm change detaches
information from its storage location, distribution system
implementation, and means of transportation, thereby, simplifying
information discovery and retrieval.

Questions
=========

1.  How can a computer network be classified?

2.  What are the differences between the Internet and the WWW?

3.  Is the Internet a private or public network? Substantiate your
    answer.

4.  How do tier 1 and tier 2 ISPs differ?

5.  How does IP-routing work?

6.  How are domain names structured?

7.  What are the individual steps of the DNS look-up process?

8.  What are a content delivery network's main benefits?

9.  What are the functions of the three SDN layers?

10. How does an overlay network work?

References
==========

Babay A, Danilov C, Lane J, Miskin-Amir M, Obenshain D, Schultz J,
Stanton J, Tantillo T, Amir Y (2017) Structured overlay networks for a
new generation of internet services. Paper presented at the
international conference on distributed computing systems (ICDCS),
Atlanta, GA, 5--8 June 2017

Bagad VS, Dhotre IA (2009) Computer networks -- II. Technical
Publications, Pune, Maharashtra

Baker FJ (2009) Core protocols in the internet protocol suite.
[https://tools.ietf.org/id/draft-bakerietf-core-04.html.](https://tools.ietf.org/id/draft-baker-ietf-core-04.html)
Accessed 19 Sept 2019

Bartolini N, Casalicchio E, Tucci S (2003) A walk through content
delivery networks. Paper presented at the international workshop on
modeling, analysis, and simulation of computer and telecommunication
systems, Orlando, FL, 12--15 Oct 2003

Baumann R, Heimlicher S, Strasser M, Weibel A (2007) A survey on routing
metrics. [http://rainer.](http://rainer.baumann.info/public/tik262.pdf)

> [baumann.info/public/tik262.pdf](http://rainer.baumann.info/public/tik262.pdf).
> Accessed 19 Sept 2019

References

Bellman R (1958) On a routing problem. Q Appl Math 16(1):87--90

Benzekki K, El Fergougui A, Elalaoui AE (2017) Software-defined
networking (SDN): a survey. Secur Commun Netw 9(18):5803--5833

Berners-Lee T, Bray T, Connolly D, Cotton P, Fielding R, Jeckle M,
Lilley C, Mendelsohn N, Orchard D, Walsh N, Williams S (2004)
Architecture of the world wide web, vol 1 W3C. [https://
www.w3.org/TR/webarch/](https://www.w3.org/TR/webarch/). Accessed 19
Sept 2019

Braga R, Mota E, Passito A (2010) Lightweight DDoS flooding attack
detection using NOX/OpenFlow. Paper presented at the IEEE local computer
network conference, Denver, CO, 10--14 Oct 2010

Cerf V, Kahn R (1974) A protocol for packet network interconnection.
IEEE Trans Commun 22 (5):637--648

Cerf V, Sunshine C (1974) Specification of internet transmission control
program. [https://tools.ietf.
org/html/rfc675](https://tools.ietf.org/html/rfc675). Accessed 19 Sept
2019

Chandramouli R, Rose S (2006) Challenges in securing the domain name
system. IEEE Comput Soc 4(1):84--87

Chapin L (1992) Charter of the internet architecture board (IAB).
[https://tools.ietf.org/html/rfc1358.](https://tools.ietf.org/html/rfc1358)
Accessed 19 Sept 2019

Chiosi M, Clarke D, Willis P, Reid A, Feger J, Bugenhagen M, Khan W,
Fargano M, Cui C, Deng H, Benitez J, Michel U, Damker H, Ogaki K,
Matsuzaki T, Fukui M, Shimano K, Delisle D, Loudier Q, Kolias C,
Guardini I, Demaria E, Minerva R, Manzalini A, López D, Salguero FJR,
Ruhl F, Sen P (2012) Network functions virtualisation: an introduction,
benefits, enablers, challenges & call for action. Paper presented at the
SDN and OpenFlow world congress, Darmstadt, 22--24 Oct 2012

Cisco (2011) Content delivery network (CDN) federations: how SPs can win
the battle for contenthungry consumers.
[https://www.cisco.com/c/dam/en/us/products/collateral/video/videoscapedistribution-suite-service-broker/cdn\_vds\_sb\_white\_paper.pdf.](https://www.cisco.com/c/dam/en/us/products/collateral/video/videoscape-distribution-suite-service-broker/cdn_vds_sb_white_paper.pdf)
Accessed 19 Sept 2019

Cisco (2018) Cisco visual networking index: forecast and trends,
2017--2022. [https://www.cisco.
com/c/en/us/solutions/collateral/service-provider/visual-networking-index-vni/white-paperc11-741490.html.](https://www.cisco.com/c/en/us/solutions/collateral/service-provider/visual-networking-index-vni/white-paper-c11-741490.html)
Accessed 19 Sept 2019

Comer D (2015) Computer networks and internets, 6th edn. Pearson
Education, London

Cooper I, Tomlinson G (2001) Internet web replication and caching
taxonomy. [https://tools.ietf.org/
html/rfc3040](https://tools.ietf.org/html/rfc3040). Accessed 19 Sept
2019

Deering S, Hinden R (1995) Internet protocol, version 6 (IPv6):
specification. [https://tools.ietf.org/
html/rfc1883](https://tools.ietf.org/html/rfc1883). Accessed 16 Sept
2019

Deering S, Hinden R (1998) Internet protocol, version 6 (IPv6):
specification. [https://tools.ietf.org/
html/rfc2460](https://tools.ietf.org/html/rfc2460). Accessed 19 Sept
2019

Deering S, Hinden R (2017) Internet protocol, version 6 (IPv6)
specification. [https://tools.ietf.org/
html/rfc8200](https://tools.ietf.org/html/rfc8200). Accessed 16 Sept
2019

Dehling T, Sunyaev A (2014) Information security and privacy of
patient-centered health it services: what needs to be done? Paper
presented at the 47th Hawaii international conference on system
sciences, Waikoloa, HI, 6--9 Jan 2014

Dijkstra EW (1959) A note on two problems in connexion with graphs.
Numer Math 1(1):269--271 Dougherty D, Truelove K, Shirky C, Dornfest R,
Gonze L (2002) 2001 P2P networking overview: the emergent P2P platform
of presence, identity, and edge resources. O'Reilly, Sebastopol, CA Duan
Q, Toy M (2016) Virtualized software-defined networks and services.
Artech House, London

ETSI (2013) Network function virtualisation (NFV); architectural
framework. [https://www.etsi.org/
deliver/etsi\_gs/NFV/001\_099/002/01.01.01\_60/gs\_NFV002v010101p.pdf](https://www.etsi.org/deliver/etsi_gs/NFV/001_099/002/01.01.01_60/gs_NFV002v010101p.pdf).
Accessed 19 Sept 2019

ETSI (2018) Network functions virtualisation (NFV); terminology for main
concepts in NFV.
[https://www.etsi.org/deliver/etsi\_gs/NFV/001\_099/003/01.04.01\_60/gs\_NFV003v010401p.](https://www.etsi.org/deliver/etsi_gs/NFV/001_099/003/01.04.01_60/gs_NFV003v010401p.pdf)

> [pdf.](https://www.etsi.org/deliver/etsi_gs/NFV/001_099/003/01.04.01_60/gs_NFV003v010401p.pdf)
> Accessed 19 Sept 2019

Falk A (2009) Definition of an internet research task force (IRTF)
document stream. [https://tools.](https://tools.ietf.org/html/rfc5743)

> [ietf.org/html/rfc5743.](https://tools.ietf.org/html/rfc5743) Accessed
> 19 Sept 2019

Fall KR, Stevens RW (2011) TCP/IP illustrated, vol 1. Addison-Wesley,
Ann Arbor, MI

Ford LR, Fulkerson DR (1956) Maximal flow through a network. Can J Math
8(1):399--404

Fotiou N, Nikander P, Trossen D, Polyzos GC (2010) Developing
information networking further: from PSIRP to PURSUIT. Paper presented
at the international conference on broadband communications, networks
and systems, Athens, 25--27 Oct 2010

Frazer KD, Merit Network Inc., National Science Foundation (1996)
NSFNET: a partnership for high-speed networking: final report,
1987--1995. Merit Network, Ann Arbor, MI

Galán-Jiménez J, Gazo-Cervero A (2011) Overview and challenges of
overlay networks: a survey. Int J Comput Sci Eng Surv 2(1):19--37

Giotis K, Argyropoulos C, Androulidakis G, Kalogeras D, Maglaris V
(2014) Combining OpenFlow and sFlow for an effective and scalable
anomaly detection and mitigation mechanism on SDN environments. Comput
Netw 62(7):122--136

Gokhale AA (2005) Introduction to telecommunications. Thomson/Delmar
Learning, Clifton Park,

> NY

Google (2012) Inter-datacenter WAN with centralized TE using SDN and
OpenFlow. [https://www.
opennetworking.org/wp-content/uploads/2013/02/cs-googlesdn.pdf.](https://www.opennetworking.org/wp-content/uploads/2013/02/cs-googlesdn.pdf)
Accessed 19 Sept 2019

Grance T, Hash J, Peck S, Smith J, Korow-Diks K (2008) Security guide
for interconnecting information technology systems.
[https://nvlpubs.nist.gov/nistpubs/Legacy/SP/
nistspecialpublication800-47.pdf](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-47.pdf)

Hinden R, Deering S (2006) IP version 6 addressing architecture.
[https://tools.ietf.org/html/rfc4291.](https://tools.ietf.org/html/rfc4291)
Accessed 19 Sept 2019

Hofmann M, Leland RB (2005) Content networking: architecture, protocols,
and practice. The Morgan Kaufmann series in networking. Morgan Kaufmann,
San Francisco, CA

Hornig C (1984) A standard for the transmission of IP datagrams over
ethernet networks. [https://
tools.ietf.org/html/rfc894.](https://tools.ietf.org/html/rfc894)
Accessed 19 Sept 2019

Huang D, Wu H (2018) Mobile cloud computing: foundations and service
models. Elsevier, Cambridge, MA

Hunt C (2002) TCP/IP network administration, 3rd edn. O'Reilly Media,
Sebastopol, CA

ICNRG (2018) Information-centric networking research group.
[https://irtf.org/icnrg.](https://irtf.org/icnrg) Accessed 1 Dec 2018

IETF (1989a) Requirements for internet hosts -- application and support.
[https://tools.ietf.org/html/
rfc1123.](https://tools.ietf.org/html/rfc1123) Accessed 16 Sept 2019

IETF (1989b) Requirements for internet hosts -- communication layers.
[https://tools.ietf.org/html/
rfc1122.](https://tools.ietf.org/html/rfc1122) Accessed 16 Sept 2019

IETF (2003) A model for content internetworking (CDI).
[https://tools.ietf.org/html/rfc3466.](https://tools.ietf.org/html/rfc3466)
Accessed 16 Sept 2019

Information Sciences Institute (1981) Transmission control protocol.
[https://tools.ietf.org/html/
rfc793.](https://tools.ietf.org/html/rfc793) Accessed 16 Sept 2019

Jacobson V, Smetters D, Thornton J, Plass M, Briggs N, Braynard R (2009)
Networking named content. Paper presented at the 5th international
conference on emerging networking experiments and technologies, Rome,
1--4 Dec 2009

Jordana J (2002) Governing telecommunications and the new information
society in Europe. Edward Elgar, Cheltenham

Kozierok CM (2005) The TCP/IP guide: a comprehensive, illustrated
internet protocols reference. No Starch Press, San Francisco, CA

Kutscher D, Eum S, Pentikousis K, Psaras I, Corujo D, Saucez D, Schmidt
T, Waehlisch M (2016) Information-centric networking (ICN) research
challenges. [https://www.rfc-editor.org/pdfrfc/
rfc7927.txt.pdf.](https://www.rfc-editor.org/pdfrfc/rfc7927.txt.pdf)
Accessed 16 Sept 2019

Li J (2008) On peer-to-peer (P2P) content delivery. Peer Peer Netw Appl
1(1):45--63

Little RG (2012) Software-defined networking is not OpenFlow, companies
proclaim. [https://
searchnetworking.techtarget.com/news/2240158633/Software-defined-networking-is-notOpenFlow-companies-proclaim](https://searchnetworking.techtarget.com/news/2240158633/Software-defined-networking-is-not-OpenFlow-companies-proclaim).
Accessed 4 Sept 2019

References

Little RG (2013) InCNTRE's OpenFlow SDN testing lab works toward
certified SDN product.
[https://searchnetworking.techtarget.com/news/2240186631/InCNTREs-OpenFlow-SDN-test
ing-lab-works-toward-certified-SDN-product](https://searchnetworking.techtarget.com/news/2240186631/InCNTREs-OpenFlow-SDN-testing-lab-works-toward-certified-SDN-product).
Accessed 4 Sept 2019

Malatras A (2015) State-of-the-art survey on P2P overlay networks in
pervasive computing environments. J Netw Comput Appl 55(1):1--23

Mansfield KC, Antonakos JL (2009) Computer networking for LANS to WANS:
hardware, software and security. Cengage Learning, Boston, MA

Mills DL, Braun H (1987) The NSFNET backbone network. ACM SIGCOMM Comput
Commun Rev 17(5):191--196

Mockapetris P (1983a) Domain names -- concepts and facilities.
<https://tools.ietf.org/html/rfc882>. Accessed 16 Sept 2019

Mockapetris P (1983b) Domain names -- implementation and specification.
[https://tools.ietf.org/
html/rfc883](https://tools.ietf.org/html/rfc883). Accessed 16 Sept 2019

NIST (2013) Security and privacy controls for federal information
systems and organizations.
[https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf.](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r4.pdf)
Accessed 16 Sept 2019

Norton WB (2011) The internet peering playbook: connecting to the core
of the internet, 2nd edn. DrPeering Press, Palo Alto, CA

Open Networking Foundation (2012) Software-defined networking: the new
norm for networks.
[https://www.opennetworking.org/images/stories/downloads/sdn-resources/white-papers/wpsdn-newnorm.pdf](https://www.opennetworking.org/images/stories/downloads/sdn-resources/white-papers/wp-sdn-newnorm.pdf).
Accessed 16 Sept 2019

Pathan M, Buyya R, Vakali A (2008) Content delivery networks: state of
the art, insights, and imperatives. In: Buyya R, Pathan M, Vakali A
(eds) Content delivery networks. Lecture Notes electrical engineering,
vol 9. Springer, Berlin, pp 3--32

Piliouras TC, Terplan K (1998) Network design: management and technical
perspectives. CRC Press, London

Robinson D (2017) Content delivery networks: fundamentals, design, and
evolution, 1st edn. Wiley, Hoboken, NJ

Saltzer JH, Reed DP, Clark DD (1984) End-to-end arguments in system
design. ACM Trans Comput Syst 2(4):277--288

Savitz E (2012) Netflix shifts traffic to its own CDN; Akamai, Limelight
Shrs Hit. [https://www.
forbes.com/sites/ericsavitz/2012/06/05/netflix-shifts-traffic-to-its-own-cdn-akamai-limelightshrs-hit/](https://www.forbes.com/sites/ericsavitz/2012/06/05/netflix-shifts-traffic-to-its-own-cdn-akamai-limelight-shrs-hit/).
Accessed 4 Sept 2019

Sitaraman RK, Kasbekar M, Lichtenstein W, Jain M (2014) Overlay
networks: an Akamai perspective. In: Pathan M, Sitaraman RK, Robinson D
(eds) Advanced content delivery, streaming, and cloud services, 1st edn.
Wiley, Hoboken, NJ, pp 305--328

Stevenson A, Waite M (2011) Concise Oxford english dictionary, 12th edn.
Oxford University Press, New York, NY

Stewart B (2000) CSNET -- computer science network.
<https://www.livinginternet.com/i/ii_csnet>. Accessed 4 Sept 2019

Stutzbach D, Zappala D, Rejaie R (2005) The scalability of swarming
peer-to-peer content delivery. Paper presented at the international
conference on research in networking, Waterloo, ON, 2--6 May 2005

Subramanian S, Voruganti S (2016) Software-defined networking (SDN) with
OpenStack. Packt Publishing, Birmingham

Sunyaev A, Pflug J (2012) Risk evaluation and security analysis of the
clinical area within the German electronic health information system.
Heal Technol 2(2):123--135

Sunyaev A, Leimeister JM, Krcmar H (2010) Open security issues in German
healthcare telematics. Paper presented at the 3rd international
conference on health informatics (HealthInf), Valencia, 20--23 Jan 2010

Tarkoma S, Ain M, Visala K (2009) The publish/subscribe internet routing
paradigm (PSIRP): designing the future internet architecture. In:
Tselentis G, Domingue J, Galis A et al (eds) A

> European research perspective. IOS Press, Amsterdam, pp 102--111

W3C (2017) W3C mission.
[https://www.w3.org/Consortium/mission.](https://www.w3.org/Consortium/mission)
Accessed 4 Sept 2019

Yaqub MA, Ahmed SH, Bouk SH, Kim D (2016) Information-centric networks
(ICN). In: Ahmed SH, Bouk SH, Kim D (eds) Content-centric networks: an
overview, applications and research challenges. Springer, Singapore, pp
19--33

Further Reading
===============

Berners-Lee T, Bray T, Connolly D, Cotton P, Fielding R, Jeckle M,
Lilley C, Mendelsohn N, Orchard D, Walsh N, Williams S (2004)
Architecture of the world wide web, vol 1 W3C. [https://
www.w3.org/TR/webarch/](https://www.w3.org/TR/webarch/). Accessed 19
Sept 2019

Comer D (2015) Computer networks and internets, 6th edn. Pearson
Education, London

Hunt C (2002) TCP/IP network administration, 3rd edn. O'Reilly Media,
Sebastopol, CA

Mansfield KC, Antonakos JL (2009) Computer networking for LANS to WANS:
hardware, software and security. Cengage Learning, Boston, MA

Singh MP (2005) The practical handbook of internet computing. CRC Press,
Boca Raton, Fl Tanenbaum AS, Van Steen M (2017) Distributed systems:
principles and paradigms, 2nd edn.

> Prentice-Hall, Upper Saddle River, NJ

[^1]: A backbone network establishes interconnections between two or
    more separate networks by establishing a central data path between
    them (Piliouras and Terplan 1998).
