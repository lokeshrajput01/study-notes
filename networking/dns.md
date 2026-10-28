# DNS — Domain Name System
**Date:** 27 October 2026
**Week:** 3, Day 1

## What I understood

DNS stands for Domain Name System. it basically gives us 
ip addresses for provided domain names so we can connect 
to the right destination.


the four step DNS query flow:-

Step 1 - Resolver
it checks its cache first for the domain's ip address.
if it is there it returns it directly to our laptop.
if not it asks a root server.

Step 2 - Root Server
it does not know the ip address of the domain directly.
but it knows which TLD server handles that domain extension
like .com or .org so it points the resolver there.

Step 3 - TLD (Top Level Domain)
handles domain extensions like .com, .org, .net, .uk, .jp etc.
it knows which authoritative server is responsible for the 
specific domain so it points the resolver there.

Step 4 - Authoritative Server
this server has the actual ip address of the domain.
it provides records about the domain like hostname and subdomains.
it gives the ip address back to the resolver.
the resolver returns the ip to our laptop and caches it 
for next time.

DNS Caching:-
dns caching stores the ip address of a domain after the 
first lookup so next time it can connect faster without 
going through the full four step process.

Security risk — DNS cache poisoning:-
an attacker can inject a fake ip address into a resolver's 
cache so users get sent to a malicious site instead of the 
real one. SOC analysts watch for this.

## What confused me
When i run nslookup command  i saw server is unknown
also i saw my default gateway ip address by confirming through ipconfig, and i also saw non-authoritative answer. this three things confused me when i saw them first time.


## Lab output - Day 1
When i run nslookup command in my cmd  for different domains. I got the server name which is unknown for every nslookup command i run for few domains then below that i got my default gateway ip address this also seen in every nslookup command.
 After this two common  things below that i saw “non-authoritative answer” for every nslookup command i run and below that i got ip addresses of the different domains in that i saw 2 ips like 1 ipv4,1 ipv6 for few domains like google.com,microsoft.com,github.com
 Etc. and also saw 2ipv4 and 2 ipv6 ip addresses for cloudflare.com and i also saw 3 ipv4 and 3 ipv6 ip addresses for other domains like amazon.com and  i also saw 4 ipv4 and 4 ipv6 ip addresses for other domains like bbc.com,youtube.com,etc
I saw different-different ip address for different domains like some has 1 ipv4,1ipv6 some has 2 ipv4,2ipv6 some has 3ipv4,3ipv6 some has 4ipv4,4ipv6 and some 1 ipv6 2 ipv4 or 1 ipv6 3 ipv4 addresses etc etc
I saw this stuff when i run nslookup command.


## One thing I can now explain without notes
dns is like a phonebook for the internet. when i type google.com my laptop asks the resolver, resolver asks root, root points to tld, tld points to authoritative server, authoritative gives the ip back. the ip gets cached so next time it is faster.

## DNS Record Types 

A Records - this maps hostnames to the ipv4 addresses.this provide us ipv4 addresses for the domain names.

AAAA Records - this maps hostnames to the ipv6 addresses.this provide us ipv6 addresses for the domain names.

MX Records - this records gives us mail servers with their priority numbers. Lowest number has highest priority.

CNAME Records - this records makes a hostname alias of another hostname.rather than directly storing ip addresses.It tells us this hostname is alias of this other hostname.

TXT Records - it basically stores text information and also it used for verification of domain ownership and to protect email from spoofing.

PTR Records - These map IP addresses back to hostnames
(reverse DNS lookup).


## nslookup lab - Day 2 

When I run the20 ns lookup commands for different domians i got output like yesterday.nothing new but when i run nslookup isro.gov.in i got output like this “no internal type for both ipv4 and ipv6 addresses(A+AAAA) records available for isro.gov.in”.

when i run this command nslookup -type=A google.com
 i got ipv4 address of google.com
 
when i run this command nslookup -type=AAAA google.com
 i got ipv6 addresses of google.com
 
when i run this command nslookup -type=MX gmail.com
 i got the output like mx preferences and numbers with it like 5,10,20,30,40 it shows lowest number with highest priority and then i also saw mail exchangers it shows mail servers
 
when i run this command nslookup -type=CNAME www.github.com
 i got canonical name as gihub.com so it basically makes a hostname alias of another hostname.
 
when i run this command nslookup -type=TXT google.com
 i got bunch of information like google.com text="google-site-verification=wD8N7i1JTNTkezJ49swvWW48f8_9xveREV4oB-0Hf5o"
like this type of output it is around 15-16 outputs like this.
This stores text and used for verification domain ownership and to protect email from spoofing.




## What I'll review tomorrow
Tomorrow I will 
Understand HTTP vs HTTPS.
Learn the basics of TLS.
Understand HTTP request and response structure.



