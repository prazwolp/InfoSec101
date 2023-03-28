Wireshark is a network protocol analyzer or an application that captures packets from a network connection such as from your home office or the internet. Packet is a name given to a discrete unit of data in a typical Ethernet network. 

Wireshark is the most used packet sniffer in the world. It has the following functions:

`1. Packet Capture` - Wireshark listend to a network connection in real time and then grabs entire streams of traffic i.e. thousands of packets at a time. 

`2. Filtering` - Wireshark is capable of slicing and dicing all of this random live data using filters. By applying a filter, you can obtain just the information that you need                  to see. 

`3. Visualization` - Wireshark like any good packet sniffer, allows you to dive right into the very middle of a network packet. It also allows you to visualize entire                              conversations and network streams. 


Wireshark is for example using a flashlight to look for something inside a cave. The network is the cave and wireshark is the tool that is used like a flashlight to look for things inside the cave. Wireshark is used for many uses, including troubleshooting networks that have performance issues. InfoSec professionals often use Wireshark to trace connections, view the contents of suspect network transactions and identify bursts of network traffic. 

For our example we will be using a file called `magnitude_1hr.pcap`. The `.pcap` extension file are PCAP files which are data files created using a program. These files contain packets of data of a network and are used to analyze the network characterstics. They also contribute to controlling the network traffic and determininig network status. When we open the file, we will see the results in the following way. 
![magnitude](https://user-images.githubusercontent.com/93686063/228027704-12210eba-07c4-41b7-bb59-9b67c615434f.JPG)

![colorconvo](https://user-images.githubusercontent.com/93686063/228122149-41414187-0799-42b0-b505-fa83b359a5d8.JPG)


The top window shows the individual packets in order. The second window shows a "decode" of any packet that is selected. Among which any of the lines with a `>` can be expanded to further analyze where it will show you the packet and protocol value. The last window in Wireshark will show you the hex value for the packet. 

Now click on `Statistics > HTTP > Requests` which will show you the various HTTP requests for the capture. 
![http](https://user-images.githubusercontent.com/93686063/228028816-bd1b9c85-0098-4bf4-b1e8-43c385f3df2a.JPG)

![http1](https://user-images.githubusercontent.com/93686063/228028973-110930d0-df12-4f7d-ae26-bceea4f8aff2.JPG)

Now let us look at some `Conversations` under `Statistics` 

![convo](https://user-images.githubusercontent.com/93686063/228115179-bb8f6d1a-d06a-4f30-b05d-ca7dbd3425b9.JPG)

The above reference will let us know who is talking to whom. We will select IPv4, we will see two IP addresses which are talking to one another. 

Click on the top of the packets column twice. `Packets A -> B` This is will give us a breakdown of who was chatting with what system the most. If we click on it again, it will be addressed accordingly, either in an ascending order or descending order. Now if we really want to know what those systems were saying to each other? We right click on a conversation and select `Apply as Filter > Selected > A <-> B` 

![convo1](https://user-images.githubusercontent.com/93686063/228119715-619f354c-de93-4fab-8985-767095aee59e.JPG)

We will see the following filter now, we will only see certain IP addresses, only the packet which meets the filter criteria will be displayed. Now if we right-click on any of the packets and select Follow > TCP Streams. 

![convo2](https://user-images.githubusercontent.com/93686063/228120254-f279f0df-a819-46dc-8be9-44bf9ea5f1b9.JPG)

If we go to the search bar and type in protocols then we will only see data from different protocols that are communicating with one another, for example we type in `ipv6`, we will only see ipv6. 

![convo3](https://user-images.githubusercontent.com/93686063/228120956-a22280be-fc8d-43b3-ad95-7e5ed006aad2.JPG)

This allows you to very quickly drill in on any specific protocols you are reviewing in a packet capture. Wireshark is a great tool but it does have some weaknesses. Wireshark cannot grab traffic from all of the other systems on the network under normal circumstances. On modern networks that use devices called switches, Wireshark (or any other standard packet-capturing tool) can only sniff traffic between your local computer and the remote system it is talking to. Wireshark can show malformed packets and apply color coding, it doesnt have actual alerts (`It is not an Intrusion Detection System`) Wireshark cannot help with decryption with regards to encrypted traffic. 




