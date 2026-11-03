# Ports and Attack Relevance
**Date:** 03 November 2026
**Week:** 4, Day 1

## What I understood

| Port | Protocol | TCP/UDP | Attack Relevance |
|---|---|---|---|
| 21 | FTP | TCP | Anonymous access (if enabled), credential theft over unencrypted FTP |
| 22 | SSH | TCP | Brute-force attempts, stolen credentials, tunneling abuse |
| 23 | TELNET | TCP | Cleartext credential sniffing |
| 25 | SMTP | TCP | Open relay abuse, spam, phishing infrastructure |
| 53 | DNS | TCP/UDP | DNS tunneling, cache poisoning |
| 80 | HTTP | TCP | C2 (command and control) over HTTP |
| 443 | HTTPS | TCP/UDP | C2 (command and control) over encrypted HTTPS/TLS traffic |
| 445 | SMB | TCP | SMB exploitation (e.g. EternalBlue against vulnerable SMBv1), ransomware and lateral movement |
| 3389 | RDP | TCP/UDP | Brute-force attempts, unauthorized remote access, ransomware deployment |
| 1433 | MSSQL | TCP | Exposed database, weak credentials, unauthorized database access |
| 3306 | MySQL | TCP | Exposed database, weak credentials, unauthorized database access |
| 8080 | HTTP Alt. | TCP | Exposed development servers, proxy abuse |
| 110 | POP3 | TCP | Credential theft if the connection is unencrypted |
| 143 | IMAP | TCP | Credential theft if the connection is unencrypted |
| 5985 | WinRM | TCP | Lateral movement, abuse of legitimate remote-management tools |

HTTP/1.1 and HTTP/2 commonly use TCP. HTTP/3 uses QUIC over UDP.

## What confused me

One thing that confused me is how to identify a suspicious port activity. whether it is suspicious or not.

## Lab output

**netstat -an findings:**

When i ran netstat -an command in cmd, firstly i saw active connections then below that i saw protocol,local address,foreign address and then state.

I found port 445,53,443 and this ports matched my 15 ports list.
I saw port 445 and i also saw its state as LISTENING and protocol as TCP.
I saw Bunch of port 53 in foreign address and i also saw there state as TIME_WAIT and there protocol as TCP.
I saw Bunch of port 443 in foreign address and i also saw there state but there state is varying for every 443 port, i saw some has ESTABLISHED,some has TIME_WAIT,some has CLOSE_WAIT and There protocol is TCP.
I also saw UDP protocol  with port 443 in foreign address but i didn’t see the state.

I noticed the ports can appear either in local address or foreign address. Local port belongs to my computer and the foreign port belong to the remote endpoint.

**nmap localhost findings:**

When i ran the nmap -sV localhost in cmd, 
i saw some information but the interesting thing is In this scan, Nmap reported two open TCP ports among the ports it scanned 135 and 445, 
the first one is 135 and its protocol as TCP and i saw its state as open,i saw its service  and verion also.
The second one is 445 and its protocol is also TCP and i also saw its state as open, i also its service but didnt saw version.

The port 445 is associated with SMB and its attack relevance SMB exploitation.

## One thing I can now explain without notes
Port numbers help a SOC analyst identify the service associated with a network connection and investigate whether its activity is suspicious.

## What I'll review tomorrow
Tomorrow I will study Firewall vs Proxy vs 
IDS/IPS vs WAF.

