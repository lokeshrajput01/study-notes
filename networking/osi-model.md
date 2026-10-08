# OSI Model

## What is the OSI Model?

OSI stands for **Open Systems Interconnection**.

The OSI model is a conceptual 7-layer framework that explains how data is communicated between different devices over a network.

It divides network communication into different layers, where each layer has a specific role.

---

## Why is it used?

Networking is complicated, so instead of treating network communication as one large process, the OSI model divides it into smaller and easier-to-understand parts.

This helps us understand how network communication works and can also help with troubleshooting.

---

## 7 Layers

| Layer | Name | Basic Function |
|---|---|---|
| 7 | Application | Provides network services used by applications |
| 6 | Presentation | Deals with how data is represented or formatted so different systems can understand it |
| 5 | Session | Manages communication sessions between applications |
| 4 | Transport | Provides end-to-end communication between applications/processes on different devices |
| 3 | Network | Responsible for logical addressing and routing packets between networks |
| 2 | Data Link | Handles communication over a local network link and uses MAC addresses and frames |
| 1 | Physical | Deals with the actual transmission of bits through a physical medium |

---

## Important Protocols / Concepts

- **Layer 4 →** TCP / UDP / Ports
- **Layer 3 →** IP / Routing
- **Layer 2 →** Ethernet / MAC / Frames
- **Layer 1 →** Cables / Radio / Fiber / Signals

---

## Encapsulation

Encapsulation is the process of adding protocol-related information to data as it moves down the networking layers before transmission.

Each relevant layer adds its own information, such as headers, to help the data be delivered and processed.

---

## Why OSI Matters in Cybersecurity

The OSI model helps security analysts understand where network communication and problems occur.

It can help with troubleshooting and analyzing network activity by thinking about different layers.

For example:

- **Layer 2 →** MAC addresses and Ethernet traffic
- **Layer 3 →** IP addresses and routing
- **Layer 4 →** TCP/UDP and ports
- **Layer 7 →** Application protocols and services

The OSI model itself does not provide security. It is a framework that helps us understand and analyze network communication.

---

## Practical Learning

While learning the OSI model, I started connecting the concepts with real networking activity.

### Commands Used

- `ipconfig` — Used to view my system's network configuration.
- `ping 8.8.8.8` — Used to test connectivity to an IP address.
- `ping google.com` — Used to test connectivity using a domain name.

These commands helped me begin connecting networking theory with real system behavior.

---

## My Key Takeaways

- The OSI model has 7 layers.
- Each layer has a different role in network communication.
- Layer 4 → Transport → TCP/UDP and ports
- Layer 3 → Network → IP and routing
- Layer 2 → Data Link → MAC and Ethernet
- Layer 1 → Physical → Physical transmission
- The OSI model helps us understand and troubleshoot network communication.
