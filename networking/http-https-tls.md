# HTTP, HTTPS and TLS
**Date:** 29 October 2026
**Week:** 3, Day 3

## What I understood

HTTP - HTTP stands for hypertext transfer protocol. So it basically set of rules that allows browser and webserver to exchange information.

HTTPS - HTTPS  stands for hypertext transfer protocol secure. It is basically http but protected with TLS (Transport Layer security).

HTTPS is more secure than HTTP because it encrypts information it protects data in transit against tampering and eavesdropping.


TLS - TLS stands for transport layer security it is basically a security protocol that protects communication between two endpoints such as browser and web server.
Provides imp protection :-
Encryption - makes intercepted traffic unreadable without necessary cryptographic keys.
Integrity - helps to detect whether the protrcted data altered in transit or not.
Authentication - helps browser to verify server identity through certificate validation.

TLS Handshake - it happens before the HTTPS communication begins.the process is called as TLS handshake.

In simple terms:
1.browser and server negotiate supported TLS settings. 
2.server provides its digital certificate and browser validate it.
3.they establish cryptographic keys needed to protect communication
4.they protect application data like http message.

HTTP Request - a message sent from browser to web server asking to do something with it such as return a webpage.
HTTP Response - a message server sends after receiving the browser request.

Example of HTTP Request:
GET/Login HTTP/1.1 
Host: example.com


The GET is HTTP Method or requested response the login requested path, and the http/1.1 is a http version and host identifies website.

Example of HTTP Response:
HTTP/1.1 200 OK
Content -Type: text/html

The 200 ok is status code /response phrase it indicates the request succeeded.the content type describe response content 

## What confused me

I was confused about the steps of  TLS handshake and how it different from tcp threeway handshake.

TCP handshake establishes tcp connection between client and server.

While TLS handshake take over that connection and establishes security parameters and cryptographic keys to protect the communicaton



## Lab output
Today, I learned the basics of HTTP, HTTPS, TLS, and the TLS handshake. I studied the structure of HTTP requests and responses.
I have not captured traffic in Wireshark yet. I will practise this in Day 4.

## One thing I can now explain without notes

HTTP is nothing but set of rules that gives permission to browser and webserver to transfer information between them.

While HTTPS is nothing but http but it is protected by another layer it is known as TLS(transport layer security).

TLS(transport layer security) protect communication between browser and webserver.

HTTP Request is the msg sended by browser to server and HTTP Response is message sended by server after receiving the request

## What I'll review tomorrow
Capture HTTP traffic using Wireshark. 

Identify the HTTP request and response.

Examine the request method, headers, status code and response body where visible.


