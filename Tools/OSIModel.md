The OSI Model or the Open Systems Interconnection(OSI) model is a conceptual model created by the International Organization of Standardization which enables diverse communication systems to communicate using standard protocols. It is based on the concept of splitting up a communication system into seven abstract layers, each stacked one upon the last. 

![osimodel](https://user-images.githubusercontent.com/93686063/218511781-4caba4df-17a1-4936-8aa4-d775df3dcb31.JPG)

The goal of OSI model is to understand how networking works between one host to another. 


`Physical layer (Layer 1)` ->  The goal is to transfer bits from one end to another, some examples of what helps transport these bits is Ethernet cable, coaxial cable and fiber cables. Although Wifi does not use wire, it is still considered Layer 1. Repeater is something that is used to extend a wire. Multi port repeater called hub is also Layer 1 technology. 

`Data Link Layer (Layer 2)` -> Interacts with the wire, put bits on the wire and retrieve bits from the wire. So for example Network Interface cards, wifi access cards are considered Layer 2. The goal of Layer 2 is Hop to Hop meaning, it stands to move 1's and 0's from one NIC to another NIC. In order to make this possible, Layer 2 uses addressing schemes which is known as MAC Addresses. MAC addresses are 48 bits which are represented as 12 hex digits. Windows machines typically use dashes in between mac addresses such as (94-65-9C-3B-8A-E5), Linux machines typically use colons(94:65:9C:3B:8A:E5), Cisco routers typically use 4 hex digits with a dot in between(9465.9C3B.8AE5). Swictches are also in this layer, switches allow you to connect many devices to them because they aid in the accomplishment of connection. 

`Network Layer (Layer 3)` -> Layer 3 is called 'end to end', addressing scheme is done through IP addresses. IP addresses are 32 bits each represented as 4 octets, each containing 0-255. Routers consist at Layer 3 of the OSI Model. Layer 3 adds source IP address and destination IP address, layer 2 information is added at Layer 3 such as the source MAC address of the computer's NIC and destination MAC address of the router's NIC. The same thing happens again as they hop around. IP address and MAC address are independent functions but there is a protocol which ties them both together cann Address Resolution Protocol (ARP), this protocol links a Layer 3 addresss to a Layer 2 address.

![osi layer 3](https://user-images.githubusercontent.com/93686063/220359661-7a657a59-0971-4955-a44e-69324f7f2d32.JPG)

`Transport Layer (Layer 4)` -> Layer 4 is used to distinguish data streams when there are multiple services running at the same time. Layer 4 uses ports in order to address the data streams. There are 0-65535 ports and there two different types of ports, TCP and UDP. TCP favors reliability and UDP favors efficiency. When data arrives through the cables, it will have a layer 2 header and a layer 3 header and a layer 4 header which will now have information such as port number in order to figure out where the data is headed. 

`Session Layer (Layer 5) -> In the TCP/IP Model, the upcoming layers are combined together to form an Application Layer. In the OSI model, however we will differentiate into 3 different layers; the Application, Presentation and Session.` This layer is responsible for opening and closing communication between the two devices. The time between when the communication is opened and closed is known as session. The session layer ensures that the session stays open long enough to transfer all the data being exchanged, and then promptly close the session in order to avoid wasting resources. The session layer also synchronizes data transfer with checkpoints, for example if a 100 MB data is being transferred, a session layer could set a checkpoint every 5 MB, if connection is dropped then the session could be resumed from the last checkpoint. 

`Presentation Layer (Layer 6) ->` This layer is primarily responsible for preparing data so that it can be used by the application layer; this layer is responsible for translation, encryption and compression of data. Two communicating devices communicating may be using different encoding methods, so Layer 6 is responsible for translating incoming data int a syntax that the application layer of the receiving device can understand. 

![layer 6](https://user-images.githubusercontent.com/93686063/220377602-01b6f9f4-bb79-4056-92c7-3518ed010b95.JPG)


`Application Layer (Layer 7) ->` This is the only layer that directly interacts with data from the user. Software applications like web browsers and email clients rely on the application layer to initiate communications. The client software applications are not part of the application layer; rather the application layer is responsible for the protocols and data manipulation that the software relies on to present meaningful data to the user. Application layer protocols include HTTP as well as SMTP(Simple Mail Transfer Protocol is one of the protools that enables email communications). 


![tcpip](https://user-images.githubusercontent.com/93686063/226691661-82d62781-7215-40e2-9e37-5079ae264a08.JPG)

