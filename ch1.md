# Overview

Most SOHO PC's are connected to:

1. telephone network
   - publicly switched telephone network (PSTN)
   - integrated services digital netowrk (ISDN)
2. cable television nettwork (CATV)

These provide access to an Internet Service Provider (ISP) network.
At work, the PC is connected to either a:

1.  Local Area Network (LAN)
2.  Enterprise wide private network

Each enterprise wide private network is composed of multiple LANs connected by an inter-site backbone network. The networks utilize the same operational mode and protocols as the Internet itself, so they are known as **intranet**.

_Wireless Networks_ and _entertainment networks_ both use basic radio to provide an access point to the Internet.

With compression, networks support rich set of applications involving multiple media types.

# Application and networking terminology

## Data Types and their characteristics

1. Text

- Unformatted plaintext
- formatted text, richtext and enables pages and complete documents to be created
- hypertext, enables web pages to be created with an integrated set of documents (each comprising formatted text) with defined linkages between them

2. Images
   - Computer-generated images
   - digitized images
3. Video
   - sequence of digitized images, each of which is called a _frame_. With broadcast television, the video signal is in analog form and must be converted into digital. There are a number of _digitization formats_ that specify the ways to do this conversion based on the screen size. To obtain a moving picture, the frames are played out at a rate determined by the format.
4. Audio
   All audio is generated in _analog_ form. Before the signal can be stored in a computer, it must be converted using an electric circuit called **analog-to-digital converter**, which involves sampling the amplitiude of the speech/audio signal at regular time intervals. Higher sampling : better quality.

Data can either be continuous or block mode. In _continuous data_, the bit rate of the communications channel that is used must be compatible with the source data that is being generated. Compressed video data stream is generated at fixed time intervals with variable bit rates.

In _block-mode data_, the source data comprises one or more blocks of data that is/are created in a time-independednt way. _Downloading_ is when time-independent blocks of data are transferred across the network to the destination. The _round-trip delay (RTD)_ is the time interval it takes between the request being made and the contents of the block being output at the destination.

## Data Communications and networking terminology

- _simplex_: data only flows in one direction
- _half-duplex_: data flows in both-directions but only 1 at a time
- _duplex_: data flows in both directions at the same time
- _broadcast_: data output by a single source device is received by all other devices that are connected to the same network.
- _multicast_ broadcast but only to a specific subset of the devices connected to the netowrk

In the case of half-duplex and duplex, the bit rate associated with each direction can be _symmetric_ or _asymmetric_.

## Network Types

Similar to the types of data stream associated with diffrent media - continuous and block-mode - so there are two types of communications channel associated with the various network types: _circuit mode_ and _packet-mode_. The first is known as a synchronous communications cahannel since it provides a constant bit rate service at a specified rate. The second is known as an asynchronous communications channel since it provides a variable bit rate service, the actual rate being determined by the transfer rate of the packets across the network.

### Circuit - Switched

Comprised of an interconnected set of _switching offices / exchanges_ to which the subscriber terminals/ computers are connected. This type of network is known as a _circuit-switched network_ and, prior to sending any data, the source must first set up a connection through the network.

- Each subsriber terminal/computer has a unique network-wide / address associated with it and, to make a call, the source first enters the number/address of the intended communication partner.
- The local switching office / exchange sets up a connection through the network to switching office /exchange to which the destination is connected.
- If the connection is available, a message is returned to the source that it is ready for data transfer.
- After all the data has been transmitted, the source/destination sends a request for the connection to be cleared.

Messages associated with the setting up and clearing of a connection are known as _signaling messages_.

The _call/connection setup delay_ is the delay while a connection initializes.

### Packet-Switched

1. Connection Oriented.
2. Connectionless

- Each terminal/computer that is connected to the network has a unique network-wide number/address associated with it.
- Each connection utilizes only a variable portion of the bandwidth of each link and hence the connection is known as a virtual connection or, more usually, a virtual circuit (VC).

**Connection-Oriented**

1. The source terminal / computer sends a _call request_ control packet to its local PSE which contains, in addition to the address of the source and destination terminal/computer, a short identifier known as a virtual circuit identifier (VCI).
2. Each PSE has a table that specifies the outgoing link that should be used to reach each network address.
3. On receipt of the _call request_ packet, the PSE the destination address within the packet to determine the outgoing link to be used.
4. The next free VCI is then selected and two entries are made into a routing table. The first specifies the incoming link and the second specifies the outgoing link.
5. The _call request_ packet is then forwarded at each PSE along the route until the destination terminal / computer is reached.

Collectively, the VCIs that are used on the various links form the virtual circuit and, at the destination, assuming the call is accepted, a _call accepted_ packet is returned to the source of the same route.

In a connectionless netowrk, the establishment of a connection is not required and the two communicating terminals/ computers can communicate and exchange data as and when they wish. In a connectionless network, therefore, the term **router** is normally used rather than packet-switching exchange.

In both network types, each packet is stored in a memory buffer. The service offered by a connectionless network is a **best-effort service**. With this mode of operation, a sequence of packets to be received on a number of incoming links, may need forwarding to the same outoging link.This is known as a **store-and-forward**.

Types of Networks:

- Internet (packet-switched, connectionless)
- X.25 (packet-switched, connection-oriented)
- Asynchronous transfer mode (ATM) networks.

Each packet is a **cell**.

## Network QoS

The operational parameters associated with a digital communications channel through a network are known as the **network Quality of Service (QoS) parameters**.

### Circuit- Switched network

- bit rate
- mean bit error rate
- transmission delay

The mean bit error rate (BER) of a digital channel is the probability of a binary bit being corrupted during its transmission across the channel over a defined time interval.

> P_b = 1 - (1 - P)^N

In practice, most networks - both circuit-switched and packet-switched - provide an **unreliable service** which is also known as a **best-try** or **best-effort**. This means that any blocks containting bit errors will be discarded.

If only error-free blocks are acceptable, it is necessary for the sending terminal/computer to divide source infomrmation into blocks of defined maximum size and for the destination to detect when a block is missing. A **reliable service** is wehn the destination requests that the source send another copy of the missing block.

The **transmission delay** associated with a channel is determined not only by the bit rate that is used but also by delays that occur in the terminal / computer network interfaces (known as **codec delays**), plus the propagation delay of digital signals as they pass from source to destination across the network.

### Packet-Switched Network

- the maximum packet size
- mean packet transfer rate
- mean packet error rate
- mean packet transfer delay
- worst-case jitter
- transmission delay

The **mean packet transfer rate** is a measure of the average number of packets that are transferred across the network per second. The **mean packet error rate** is the probability of a received packet containing one or more bit errors.

## Application QoS

- required bit rate or mean packet transfer rate
- maximum startup delay
- maximum end-to-end delay
- maximum delay variation/jitter
- maximum round-trip-delay

The **startup delay** defines the amount of delay that elapses between an application making a request to start a session and the confirmation being received from the applicaiton at the destination that it is prepared to accept the request.

To overcome the effect of jitter a technique known as **buffering** is used.

**Packetization delay** is the additional delay incurred at the source as the information bitstream is converted into packets.

# Digital Communications Basics

In each end system there is a **network interface card(NIC)** that performs related network interface functions. The signal output by the NIC simply varies between two voltage levels (_+V_ and _-V_) at a rate determined by the transmission bit rate knwonw as **baseband transmission**.

Networks that provide a digital interface like LAN and ISDN, baseband transmission is also used over the access lines to the network. We can modulate the **carrier signal** by mixing or multiplying it with the modulator, or **modem** (**modulated transmission**).

When transmitting any type of electrical signal over a transmission line, the signal is **attenuated** (decreased in amplitude) and **distorted** (misshaen) by the transmission medium. All types of transmission medium is an electrical signal known as **noise**.

The level of signal impairment is determined by:

- type of transmission medium
- length of the transmission medium
- bandwidth of the medium
- bit rate of the data being transmitted

The received signal is at its peak amplititude in the centre of each **bit cell period**. When the receiver reads the signal at this moment, it is said to be in **synchronism** with the incoming bitstream. **Character / byte synchonism** and **block/frame synchronism** is not a trivial task.

## Transmission media

Types of transmission

- electrical wire
- fiberglass
- electromagnetic waves

### Twisted-pair lines

The proximity of the signal and ground referencce wires means that any interference signal is picked up by both wires, reducing its effect on the difference signal. If multiple twisted pairs are enclosed within the same cable, the twisting of each pair within the ecable reduces crosstalk.

\*\*Unshielded twisted pairs (UTPs) are used extensively in telephone networks and (with special integrated circuits) in many local area networks. With shielded twisted pairs (STPs), a protective screen or shield is used to reduce the effect of interference.

### Coaxial cable
