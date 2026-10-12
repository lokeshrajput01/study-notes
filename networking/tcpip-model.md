# TCP/IP Model
**Date:** 11 October 2026
**Week:** 2, Day 2

## What I understood 
today i understand what is tcp/ip model.
tcp/ip stands for transmission control protocol/internet protocol.
the tcp/ip model describes how computers communicate over a network,including internet.
it organizes network communication into 4 layers and each layer has a different job.

the four layers are:-

layer 4 application layer - this is where application level network protocols operates.
when we open browser and type url the http/https protocols creates our request and other protocols at this layer,
dns(translate domain name into ips), ftp(file transfer), smtp(email transfer).
this is where the software we use lives. 
ex. http,https,dns,smtp.

layer 3 transport layer- handles how data is delivered and moves data between applications on different devices.
tcp and udp work here and using port numbers identify applications endpoint.
tcp and udp are two main protocols of transport layer.
tcp- reliable,that checks data arrived or not.used in web browsing and emails 
udp- fast,but no checks used in gaming and video calls.udp is very useful where speed is important more than perfection.

layer 2 internet layer- handles addressing and routing for forwarding packets to their destination.
ip is important protocol here.ip lives here.
routers works at this layers decides which path our data takes across internet.
ex.ipv4,ipv6,icmp. 

layer 1 network access layer- this layer handles physical transmission. 
it actually deals with cables,wifi signal, network cards,
mac address lives here.
the main protocols here are ethernet,wifi 802.11

## How it maps to the OSI layers

Layer 4 Application → Application + Presentation + Session  
Layer 3 Transport → Transport  
Layer 2 Internet → Network  
Layer 1 Network Access → Data Link + Physical

osi has 7 layers because it separates things more precisely.
where tcp/ip practical model actually used in real networks.
osi model is a conceptual model that used for teaching and troubleshooting conversations.

## why the tcp/ip model matters in cybersecurity.
understanding tcp/ip help sec. analyst to interpret network traffic ,recognize where suspicious activity may occur,
understand communication between systems,investigate connectivity problem


## What confused me
today ip addressing and mac addressing confuse me little bit but later i understand what it is.
also i am confused that why tcp/ip model uses 4 layers as osi model uses 7 layers?

## Lab output
I ran ipconfig /all and found my private IPv4 address, subnet mask, and default gateway. 
I ran ping google.com and all packets were sent and received successfully. 
I ran arp -a and saw a list of IP-to-MAC address mappings for devices on my local network.

## One thing I can now explain without notes
tcp/ip is stands transmission control protocol/internet protocol.
the tcp/ip is a model that describes how different computers,devices communicate over networks including internet also. 
tcp/ip model organizes network communication into 4 layers each has a different job.
tcp/ip model helps to recognize where suspicious activity may occur,interpret network traffic,investigate connectivity problem.


## What I'll review tomorrow
Tomorrow I will study IPv4 addressing — what an IP address structure looks like, private vs public ranges, and what subnet mask means.
