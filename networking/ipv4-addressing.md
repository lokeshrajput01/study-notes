# IPv4 Addressing
**Date:** 12 October 2026  
**Week:** 2, Day 3

## What I understood

IP Address - Every device on network needs an address so data 
knows where to go. Think of it like a home address, if the 
address is not there so how the letter will be delivered.
It looks like 192.168.5.1
It has four numbers and three dots.
Each number is 8-bits long and that is why it is called an octet.
It is 4 octets / 4 bytes / 32-bits.

There are two types of IP Addresses:
1) Public
2) Private

Public IP Address:
It is our address on internet.
A public IP address is globally routable and generally unique, but it can be shared by multiple customers through CGNAT.
Two devices cannot use same public ip at the same time.
It is provided by our ISP (Internet Service Provider).
When we visit google.com on our browser Google sees our public 
ip address to connect with us.

IPV4 Address Classes:
Class A - 1.0.0.0 to 126.255.255.255 - 255.0.0.0
Class B - 128.0.0.0 to 191.255.255.255 - 255.255.0.0
Class C - 192.0.0.0 to 223.255.255.255 - 255.255.255.0
Class D - 224.0.0.0 to 239.255.255.255 - Multicast
Class E - 240.0.0.0 to 255.255.255.255 - Experimental

Private IP Address:
It is our home/office address.
It is not unique globally. The same ip like 192.168.5.1 is 
used in millions of homes for their routers.
Private IP addresses are not normally routed directly over the public internet.they are used inside local network.

Why private IPs exist:
IPv4 allows only 4.3 billion unique addresses.
The world has far more than 4.3 billion devices.
Private IPs allow the same addresses to be reused inside 
millions of different networks because they never appear 
on the public internet.

Private IP ranges:
range 1 - 10.0.0.0 to 10.255.255.255 - used in large organizations
range 2 - 172.16.0.0 to 172.31.255.255 - less common
range 3 - 192.168.0.0 to 192.168.255.255 - used in almost 
every home network

If you see 10.x.x.x, 172.16.x.x to 172.31.x.x, or 192.168.x.x it is a private IP address.

Default Gateway:
It is the router's private IP address.
When a device wants to communicate outside the local network 
it sends data to the default gateway first, then the router 
handles getting it to the destination.

DNS Server:
It translates domain names to IP addresses.
When we want to reach google.com the DNS server gives us 
Google's IP and then we connect through that IP.
Without DNS we would need to memorize every website's IP address.

Subnet Mask:
The device gets the IP and subnet mask when it connects 
to the local network.
The subnet mask identifies which part of the IP is the 
network part and which is the host part.

Example:
IP address:   192.168.1.5
Subnet mask:  255.255.255.0
Network part: 192.168.1
Host part:    5

For /24, the first three octets (192.168.1) are the network part, and the last octet (5) is the host part.

Why it matters:
The device uses the subnet mask to decide whether the 
destination is on the same local network or outside it.
Same network — talk directly.
Different network — send to the default gateway first.

CIDR notation (shorthand for subnet masks):
255.255.255.0 = /24 (24 bits for network, seen constantly in SOC work)
255.255.0.0   = /16
255.0.0.0     = /8

## What confused me

I found subnet masks confusing today. I need more practice understanding how a subnet mask identifies the network portion and the host portion of an IPv4 address.

## Lab output

I ran ipconfig /all. My IPv4 address starts with 192.168 
which confirms it is a private IP address.
Subnet Mask - My computer showed 255.255.x.x, which helps identify the network portion of my IPv4 address.
Default Gateway - My computer showed 10.x.x.x, which is the router address used to send traffic to destinations outside my local network.
DNS Server - My computer showed 10.x.x.x, which is the resolver Windows uses to look up domain names such as google.com.

When I searched "what is my IP" on Google it showed a 
different address from my ipconfig IP. The address shown by Google is the public IP it sees for my connection.
It may be assigned by my ISP or shared through CGNAT. The ipconfig IP is my 
private IP used only inside my local network. NAT on my 
router swaps the private IP with the public IP when 
sending data to the internet.

## One thing I can now explain without notes

IP Address: An IP address helps devices communicate with each other and makes sure data can reach the right destination. I think of it like a home address because, just as a letter needs an address to reach someone, data needs the correct destination address to reach a device.

Public vs. Private IP - A public IP address is used when communicating over the internet and is usually provided by my ISP or network provider. A private IP address is used within a local network, and the same private IP address can be used in many different homes without causing a conflict between those separate networks.

## What I'll review tomorrow

Tomorrow I will study subnetting — how to calculate 
network ranges, host ranges, and practice /24 problems.
