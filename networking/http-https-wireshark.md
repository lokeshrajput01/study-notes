# HTTP, HTTPS and TLS — Wireshark Capture
**Date:** 30 October 2026
**Week:** 3, Day 4

## What I understood

the HTTP request and response structure looks like,

HTTP Request structure has 
request method,
request uri it is the requested path,
request version it is the HTTP version, 
user-agent this gives information about client software,
Host- this identifies the targeted host.

HTTP Response structure has
Response version,
Status code, like 200
Response phrase, like ok 
The 200 ok means request succeeded
Content length, this indicates body length in bytes
Content type this describes the content type

TLS adds protection to the communication between client and server it provides encryption,integrity,authenticaton so they can exchange data securly.

I learned that \r\n represents Carriage Return and Line Feed, which are used to mark the end of lines in HTTP/1.1 messages.


## What confused me

I am confused by seeing two GET request for connecttest.txt. the only difference is between this two request is the host header and also what is  \r\n means in the http request header.

This things confused me.

## Lab output

Today i performed HTTP traffic using wireshark.

First i ran this command in windows cmd,
curl http://example.com -v 

The -v option displays detailed information about the connection and HTTP communication.

After i run this command. i had Wireshark running first.Then i opened wireshark and stop the packet capturing and applied the ‘http’ filter.

Then i observed total 6 packets in wireshark.
3 GET request and 3 200 OK response.

The 2 GET request are for /connecttest.txt
The 2 200 OK  response are for (text/plain) content type.
The 1 GET request is for the (  / ) and The 1 200 OK response is for the (text/html) content type.

When i saw each packet in the packet details pane and when i expand the http
(Hypertext transfer protocol) then i saw information about the browser and server communication.

In first GET packet (packet no.19) i saw :-
Request method is GET 
REQUEST URI the path requested is /connecttest.txt
I also saw the Requested version is HTTP/1.1
Below that i seen connection: Close \r\n
I also saw user agent: Microsoft NCSI\r\n. which gives info about client software.
And below that is saw Host: www.msftconnecttest.com\r\n which identifies the targeted host.
And in last i saw response in frame and full requested URI.

In second GET packet (packet no.20) i saw everything is similar except the,
Host: ipv6.msftconnecttest.com \r\n 
I saw it gave the ipv6 address for targeted host.

In the third packet (packet no.22) which is 200 OK Response packet i saw
The Response version is http/1.1
The Status code is 200 and its description OK
The Response phrase is OK
I saw the content length also which  is 22 
And also i seen date,day,month and time
Below that connection: close\r\n
And then i saw the content-type: text/plain\r\n it basically describes the type of content in this it is plain text.
And i also sae cache control,req. In frame,time since requested,req. Uri, full request uri, file data ,line based text data etc-etc other information.
In this the full requested URI: http://www.msftconnecttest.com/connecttest.txt]

In fourth packet (packet no.24) which is also a 200 OK response packet  i saw everything is similar as third packet  except the request in frame,time since request and the full request uri this is one thing that is different in fourth packet,
Full request URI: http://ipv6.msftconnecttest. com/connecttest.txt


In fifth packet (packet no.55) i saw request Method that is GET,
Then the request uri is /
Then the request version is HTTP/1.1
Then the host is example.com this is the targeted host
And then the user-agent is curl/8.21.0 and this the info about client software.
And in last the Accept: */*\r\n
\r\n

And in the sixth packet (packet no.58) i saw a lot of information as below,

Response Version,Status Code,status Code Description,Response Phrase as OK ,I saw date,day,month and time,
Then i saw Content-Type as text/html; charset=utf-8\r\n,Transfer-Encoding,Connection,Server,Last-Modified-date time day,Allow,Accept-Ranges,
Age,cf-cache-status,CF-RAY,alt-svc,Request in frame,Time since request,Request URI,Full request URI,
HTTP chunked response,,Data chunk (577 octets),End of chunked encoding,File Data: 577 bytes,Line-based text data: text/html (1 lines)


This is what i seen in wireshark about HTTP Request and HTTP Response.


when i ran this second command in windows cmd,

curl https://example.com -v 
After i run this command then i again reopened wireshark and applied the ‘TLS’ filter.

Then i saw TLS handshake packets.

But they are encrypted so i didnt see any information.except some details like,
Stream index,TLS v1.2 record layer: application dat protocol: hypertext transfer protocol, then i saw content type: application data(23),below that its showed the version as TLS 1.2, also it showed length as 19 and below it the encrypted application data with the number and alphabets.

So http shows information about the communication between server and browser while https encrypt the information so someone who can intercept the traffic cannot see the information.because of protection by TLS.


## One thing I can now explain without notes

The http request is the message that browser(client) sends it to webserver it tells the server to do something with my request like return me a webpage
and then the http response is sends back to the browser(client) by server after the request is received.

## What I'll review tomorrow
Tomorrow I will write the URL to page explainer — 
two pages, my own words, pulling everything together 
from weeks 2 and 3.

