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

* Each terminal/computer that is connected to the network has a unique network-wide number/address associated with it.
* Each connection utilizes only a variable portion of the bandwidth of each link and hence the connection is known as a virtual connection or, more usually, a virtual circuit (VC).
1. The source terminal / computer sends a *call request* control packet to its local PSE which contains, in addition to the address of the source and destination terminal/computer, a short identifier known as a virtual circuit identifier (VCI). 
