---
layout: post
published: true
title: Sockets Programming in Java
permalink: /sockets-programming-in-java/
wordpress_id: 447
categories:
- News
- Java
- programming
- howto
- connectionless protocol
- UDP
- communication protocol
- client / server
- TCP protocol
- stream communication protocol
- control protocol
- connection session protocol
- user datagram protocol
- Communication Protocols
- transfer control protocol
- server applications
---


Java can as many other programming languages be used to write and develop client / server applications. This guide introduces the fundamental concept and techniques related to socket programming in Java.

<strong>Communication Protocols</strong>
There are two major communication protocols for IP-based networks and usable in relation to socket programming; datagram communication and stream communication. The datagram based communication protocol aka <a href="http://en.wikipedia.org/wiki/User_Datagram_Protocol">UDP (user datagram protocol)</a> is a connectionless protocol. This means that every time datagrams are about to be sent, the local socket descriptor and the receiving socket's address should also be defined every time. The stream communication protocol, known as <a href="http://en.wikipedia.org/wiki/Transmission_Control_Protocol">TCP (transfer control protocol)</a>, which unlike UDP is a connection session protocol - rather than the UDP - the connectionless protocol. Communication over the TCP protocol is done by first establishing a connection a pair of sockets. One socket is defined as a server socket - a socket which listens for connections. While the other socket asks the server for a connection - this is defined as the client socket. Once the connection is established, the sockets can be used to transmit data.

<strong>Opening a socket to a server on ip 10.10.10.1 and port 4242 in Java</strong>
<code lang="java">
Socket TestClient;
TestClient = new Socket("10.10.10.1", 4242);

```



<strong>Opening of a server socket that listens on port 4242</strong>
<code lang="java">
// create a server socket
ServerSocket TestService;
TestServervice = new ServerSocket(4242);

// create a socket object from the serversocket object
Socket s = TestServervice.accept();

// connection notification
System.out.println("Client Accepted");

// init input stream reader
BufferedReader rd = new BufferedReader(new InputStreamReader(s.getInputStream()));

// read a line and print in the console
System.out.println(rd.readLine());

// init write back stream 
PrintWriter wr = new PrintWriter(new OutputStreamWriter(s.getOutputStream()),true);

// do the actual write back to the client
wr.println("Hello World");

```
