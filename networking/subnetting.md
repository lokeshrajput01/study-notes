# Subnetting
**Date:** 15 October 2026
**Week:** 2, Day 4

## What I understood — 

**What is a network address and what is a broadcast address?**

A network address is the starting/first address of the network. 
A broadcast address is the last address of the network it is in the end of the network.

**Why we subtract 2 from total addresses to get usable hosts?**

because these addresses are reserved for network address and broadcast address. so that's why we subtract 2 from total addresses.
we cannot use these 2 addresses for hosts.

**What /24 means and what its subnet mask is?**

/24 means the first 24 bits are network bits. In the subnet mask 255.255.255.0, those bits are 1s in binary, while the remaining 8 host bits are 0s.

## What confused me — 

I got few questions wrong out of during the time of practice round 1 for (/24) problems. after the round i took a retest and in that i got all correct answers.

(1)For 192.168.100.0/24, how many total IP addresses are in the subnet?
My answer: 255  but actual answer is 256

(2)For 192.168.50.10/24, how many usable host addresses are available?
My answer: 253  but actual answer is 254

(3)For 192.168.2.150/24, what is the last usable host address?
My answer: 192.168.2.253  but actual answer is 192.168.2.254

(4)For 192.168.8.0/24, give the complete usable host range.
My answer: 192.168.8.0-192.168.8.255  but actual answer is 192.168.8.1–192.168.8.254

(5) A subnet has IP 10.0.9.0/24. Give the network address, first usable host, last usable host, broadcast address, and total usable hosts.
My answer: 10.0.9.0 ,10.0.9.1 ,10.0.9.254 ,10.0.9.255 ,253 usable host  but actual answer is 254 usable host

I mixed up some things from the subnet mask like total vs usable,host range boundaries and i got few answers incorrect.


## Lab output — write your actual scores: 

Round 1: i got 15 correct out of 20

Round 2 retry: i got all correct out of 6


## One thing I can explain without notes —
subnetting is changing subnet mask to suit our needs.
Subnetting is dividing a large network into smaller networks so IP addresses can be used more efficiently.
subnet mask tells us which part is network part and which part is host part in the 32 bits IP address.which also called as 4 octet or 4 bytes because 8 bits = 1 octet / 1 byte

## What I’ll review tomorrow — 
Tomorrow I will study /25 and /26 subnetting problems, then cover NAT, ARP, and ICMP.
