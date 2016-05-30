# Networking Questions
------
These are questions related to networking and protocol concepts. 


======
#### TCP/IP
------

+ **What port does `ping` use?**

   Trick question. The `ping` utility sends ICMP echo requests, which is part of the protocols within the IP 
suite. As such, it functions at a lower level than TCP or UDP, and does not use ports. 

+ **What service commonly runs on port X?**

   Wikipedia has [an exhaustive list](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers) of 
ports and their common protocols. Some major ones to remember are:

   Port | Protocol
   --- | --- 
   tcp/21   | `ftp` 
   tcp/22   | `ssh` 
   tcp/23   | `telnet` 
   tcp/25   | `smtp`
   udp/53   | `dns`
   tcp/80   | `http`
   tcp/443  | `https`

+ **What is the difference between TCP and UDP connections?**

    They're almost polar opposites. Some of the key differences:

    TCP                 | UDP
    ------------------- | --------------
    Connection-oriented | Connectionless
    Data stream         | Series of separate datagrams
    Packets are ordered, and rearranged to be in-order | Packets are treated as independent. Applications handle ordering 
    Error Correction    | No Error Correction
    Flow Control        | No Flow Control
    Lots of overhead    | No overhead
    High latency        | Low latency
    Used commonly for FTP, SSH, Telnet, HTTP | Used commonly for DNS, VOIP, P2P filesharing 

+ **Explain the TCP 3-way handshake and 4-way teardown process.**

    TCP, being connection-oriented, uses a 3-way handshake to begin a session with a remote server. The steps 
are as follows:

    + `SYN` - Client sends a TCP packet with the SYN flag set.
    + `SYN ACK` - Server responds with a TCP packet that has both the SYN and ACK flags set.
    + `ACK` - Client acknowledges the server's response by sending a TCP packet with only the ACK flag set.

    Connection termination/teardown is similar, but a 4-way handshake instead:

    + `FIN` - Client sends a TCP packet with the FIN flag set.
    + `ACK` - Server responds with a TCP packet with the ACK flag set.
    + `FIN` - Server sends a separate TCP packet with the FIN flag set when it's ready to end the connection.
    + `ACK` - Client responds with a TCP packet that has the ACK flag set. The connection is now terminated.

======
#### DNS
------

+ **When would DNS use TCP instead of UDP?**

   Zone transfers that are too large to fit in a single UDP packet are handled via TCP instead.


======
#### HTTP
------

+ **What are some common HTTP request methods?**

   Most people are familiar with `GET` and `POST`, conventionally used for requesting and sending data, 
respectively. Definitions can be found for others in [the RFC2616 
specification](https://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html).

   `HEAD` is another request method often seen in the wild, though not nearly as common as `GET` or `POST`. 
Its function is the same as `GET`, except the standards require the server to not return a message body in 
the response. Instead, the server only sends back metadata surrouding the requested resource. `HEAD` is sometimes 
used in requests with remote exploits, as a means of bypassing IDSs and filters that only screen `GET` or 
`POST` requests.
