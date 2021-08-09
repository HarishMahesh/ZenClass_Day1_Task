# Difference between HTTP1.1 vs HTTP2

HTTP/1.1 has been around for more than a decade. With Google’s SPDY leading the way in 2015, the IETF (Internet Engineering Task Force) gave us HTTP/2, 
which introduces several features to reduce page load times.

HTTP/2 achieves faster webpage loading without performance optimizations that require extensive human efforts in terms of development. 
It significantly reduces the complexities that had crept into HTTP/1.1 and gives us a robust protocol which, though not without its flaws, 
will perhaps stand the test of time. Before making this leap forward, let’s trace our steps back to when the internet was in its infancy to understand how the 
different versions evolved into the current form.

### year of origin

HTTP/1.1 - 1997

HTTP/2 -  2015

### Key Features

HTTP/1.1 - It supports connection reuse i.e. for every TCP connection there could be multiple requests and responses, and pipelining where the client can request 
           several resources from the server at once. However, pipelining was hard to implement due to issues such as head-of-line blocking and was not a feasible solution.

HTTP/2 -   Uses multiplexing, where over a single TCP connection resources to be delivered are interleaved and arrive at the client almost at the same time. It is done using 
           streams which can be prioritized, can have dependencies and individual flow control. It also provides a feature called server push that allows the server to send data 
           that the client will need but has not yet requested.
           
### Status Code

HTTP/1.1 - Introduces a warning header field to carry additional information about the status of a message. Can define 24 status codes, error reporting is quicker 
           and more efficient.

HTTP/2 -   Underlying semantics of HTTP such as headers, status codes remains the same.

### Web Traffic

HTTP/1.1 - HTTP/1.1 provides faster delivery of web pages and reduces web traffic as compared to HTTP/1.0. However, TCP starts slowly and with domain sharding 
           (resources can be downloaded simultaneously by using multiple domains), connection reuse and pipelining, there is an increased risk of network congestion.

HTTP/2 -   HTTP/2 utilizes multiplexing and server push to effectively reduce the page load time by a greater margin along with being less sensitive to network delays.

### Header Compression

HTTP/1.1 - Headers are sent on every request leading to a lot of duplicate data being sent uncompressed across the wire.

HTTP/2 -   Header compression is included by default in HTTP/2 using HPACK.

### Protocol Type

HTTP/1.1 - Text based protocol that is in the readable form.

HTTP/2 -   It is a binary protocol (HTTP requests are sent in the form of 0s and 1s). Needs to be converted back from binary in order to read it.



