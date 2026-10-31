When we type google.com and press enter our device follow this steps below to reach on google.com,

In the first step we need ip address of the google.com so we can reach to it,
So it performs four-step dns query flow as follows,

Step 1 is recursive resolver it checks that the ip address of google.com is already stored in its cache or not if it is there its sends the ip address directly to our device. If it is not there it asks from root server or queries it from root server.
Step 2 is root server it directly does not provide ip address of requested domain,but it knows which TLD server has ip address of that domain basically it points out resolver there.
Step 3 is TLD(top level domain) it handles domain extensions like .com, .org, .net and country level extensions also like .uk, .jp,  .ph etc and it knows which authoritative server has the ip address of requested domain so it points resolver there.
Step 4 is authoritative server this server has the information and dns records that also includes ip address so it provides the actual ip address to resolver and it return it to our device and saved it to its cache so next time when we want to go on google.com it can send it fast no need to perform the four-step dns query flow.


Then the Subnet mask decides the routes:-
It basically checks that if the device want to communicate is on local network or outside that local network. If it is inside local network it communicate directly. If it is outside local network it sends it to default gateway first. Then the router helps that data to reached its destination.

After that arp finds the gateway MAC address that is associate with its ipv4 address on local network. 
Arp checks its  arp cache if the gateways MAC address is already saved in it or not,if it is not there it broadcast a arp request on same local network,that who has the ip address so device with same ip address return its MAC address. So our device can now sends frames to MAC.

Then NAT translates the private ip address to public ip address and public to private. so the device can sends data from local network to outside local network basically to internet. So we can reach google.com. Its need public ip address because it is our address on internet and it is unique across the world and two devices cannot use it at same time it is provided by our ISP. while private ip address is our address at local network it is not unique globally and it cannot travel on internet it can only used inside local network thats why NAT translates Private ip to Public ip address.

Then to establish connection between client and server the TCP three-way handshake used, it has 3 steps;
SYN- in this step client(browser) sends a synchronize packet  to server by saying “i want to communicate.”
SYN-ACK-in this step the server replies with “i received your request and i am ready to communicate are you ready for it?”
ACK-in this step the client replies with “i am ready, lets communicate.”

Then the connection get established and now we can exchange data between client and server.

After this TLS handshake encrypts this connection, it is used to protect the communication between client and server. So someone who can intercept the traffic cannot read the data or tls protect it against tampering and eavesdropping.
It provides important protection like 
Encryption-this make intercepted traffic unreadable without the necessary cryptographic keys.
Integrity-its helps to detect whether data in transit is altered or not.
Authentication-this helps our browser to verify servers identity through certificate validation.

“TLS handshake happens after the TCP handshake and before any HTTP data is sent.” 

Then the HTTP Request travel through TCP/IP Layers-
In this the browser sends a message to server to get webpage like google.com
It include the the http method-GET,requested path,HTTP Version,host which identifies the targeted host,user agent it tells information about the client software,etc 

It travel through the tcp/ip layers,
Application layer-this layer creates our request like HTTP,HTTPS
Transport layer-this layer tells how to will be delivered in our case it will delivered through TCP because it is reliable and connection oriented it checks whether data is delivered or not if it is not delivered it can be resend by it.and it uses port number to identify the endpoints of application.
Internet layer-in this layer ip address of source and destination added and it uses ip info and routing to forward the packets towards destination.
Network acces layer-this layer handles physical transmission ethernet and wifi handles local link information and then it sends the frame.


This process is called encapsulation because at each relevant layer addition information get attached. And at the receiver end it happens in reverse to read the inormation attached by each data it is known as decapsulation.

After this the server response with 200 OK response which tells the request succeeded.
In this the server sends back the message after receiving the request and then it actually returns the webpage.
It includes HTTP Version,status code 200 OK ,Content-Type it describes the content type,Content-Length it indicates body length in bytes and HTML Content it is response body.etc 

And after this steps finally the browser loads google.com

A SOC analyst monitoring this flow watches for anomalies at each step — unusual DNS queries, unexpected ports, suspicious TLS certificates, or abnormal HTTP responses.

