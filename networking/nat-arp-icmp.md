# NAT, ARP, and ICMP
**Date:** 16 October 2026
**Week:** 2, Day 5

## What I understood

NAT - NAT stands for Network Address Translation.
nat basically helps to translates the set ip addresses with another set of ip addresses.
nat translates private to public and public to private.
NAT sits on your router. 
The router is what actually does the translation, not your laptop or the destination server.
it helps to preserves the limited amount ipv4 public ip addresses.

ARP - ARP stands for Address Resolution Protocol.
arp helps us to find the destinations mac address that associated with the ipv4 address on local network.
imagine if our computer wants to send data to another device,it will check if it have already that mac address in arp cache or not then if it is not there
it will broadcat a arp request on that local network so the request will be recieved to the device and it will reply it with hey its me and this is my mac address.
now it will be save in the arp cache and we can communicate with each other.


ICMP - ICMP stands for Internet Control Message Protocol.
it helps the network devices to sends the error reports and diagnostics information about ip communication.
icmp helps to report network conditions and network connectivity.
when we use ping our computer uses icmp messages to test another device is reachable or responding.


## What confused me
today icmp confused me little becuase where it is used and why it is needed.
later i understand it is needed in the network layer for sending the error reports and diagnost the information.
ip itself does not provide diagnostic and error-reporting messages, so ICMP complements ip.

## Lab output

I ran `arp -a` and saw two interface sections. 
I identified my Wi-Fi interface using `ipconfig`. 
I observed Internet Address, Physical Address, and Type columns. 
My default gateway entry was dynamic, while most other entries were static. 
Some static entries started with `239.`, which are multicast addresses.

## One thing I can now explain without notes
When a device wants to reach something on a different network,
ARP does not broadcast for the destination device directly.
Instead the device sends an ARP request for the default 
gateway's MAC address. The router then handles forwarding 
the packet to the other network.

## What I'll review tomorrow
Tomorrow I will study the three-way handshake and capture
a real SYN/SYN-ACK/ACK in Wireshark.
