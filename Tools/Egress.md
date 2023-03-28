In Cyber, specifically in networking,

`Egress in the world of networking implies the traffic that exits an entity or a network boundary`

`Ingress is the traffic that enters the boundary of a network`

We will be doing some traffic analysis in order to find threats. We will be using a tool called Real Intelligence Threat Analytics (RITA). The analysis will help us detect command and control traffic on a network. First we will go to Tools and find a report for the hours we have been monitoring. Once we pull the report out, we will go to individual databases to further deep dive into our data to find machines that are communicating with the C2 servers with the threat actor. 

![photo_2023-03-28_10-01-37](https://user-images.githubusercontent.com/93686063/228281442-12b8533a-7c25-406a-af30-8e1dabd31441.jpg)

![photo_2023-03-28_10-04-47](https://user-images.githubusercontent.com/93686063/228282109-8da73028-f20c-4ed1-b245-659b4f52839e.jpg)

We will select the `Beacons`. Some backdoors have a very strong heartbeat which is when a backdoor will consistently reconnect to get commands from an attacker at a speific interval. The interval consistency of the heartbeat is the TS score where a value of 1 is perfect. 

Now lets look at another example of a backdoor. 

![photo_2023-03-28_11-33-17](https://user-images.githubusercontent.com/93686063/228307912-6dbfa3e7-26b2-4a19-83e1-fd6b9cb43e5f.jpg)

We can clearly see that this particular connection is not beaconing back to a specific IP address. There is hardly any connections that stand out and the duration is not very frequent as the other ones. This connection beacons back to a DNS server which is very crafty and a unique way of doing things. 

![photo_2023-03-28_11-36-12](https://user-images.githubusercontent.com/93686063/228308479-eb10fd4a-8fec-4bb0-ae10-b70ef5eb0902.jpg)

If we were to go look under `DNS`, we can see that the com domain is pretty common but it is also making 40,000 connections to a `nanobotninjas.com` domain which is fishy because it is not normal. Other connections are pretty common but this particular one stands out. 

Now let us use this datasheet that we have in order to have a broader picture of the attack that might be happening. We will use a tool called `AC Hunter`. 

![photo_2023-03-28_11-40-21](https://user-images.githubusercontent.com/93686063/228309519-228211f1-0ef0-4d44-b19e-041f493b02f7.jpg)

We will pick `vsagent` in order to learn more about the things it is doing in the network. We can see multiple aspects of the system connections which can help us to know more about the data. We can see if there are any connections that had a threal intel hit, or if there are any connections that have beacons to a fully qualified domain. 

![photo_2023-03-28_11-44-49](https://user-images.githubusercontent.com/93686063/228310538-8a2703cd-b275-485c-a510-47b75d6b63a2.jpg)


This tool gives us an indpeth look at the connection and what it might be doing in the system. MITRE ATT&CK can be used in order to map out how things are connnected by the threat actor. 


