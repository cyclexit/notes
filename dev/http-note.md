# HTTP Note

## Index
* [MIME Type](#MIME-Type)
* [URI](#URI)
* [HTTP Message](#HTTP-Message)
  * [Message Structure](#Message-Structure)
  * [Methods](#Methods)
  * [Status Code](#Status-Code)
* [Connections](#Connections)
  * [TCP/IP](#TCP/IP)
* [Architectural Components of the Web](#Architectural-Components-of-the-Web)

## MIME Type
MIME = Multipurpose Internet Mail Extensions </br>
MIME is represented as a primary object type and a specific subtype. </br>
[MIME type list](https://www.freeformatter.com/mime-types-list.html)

## URI
URI = Uniform Resource Identifier
* URL(Uniform Resource Locator)
  1. schema: describe the protocal used to access the resource(e.g., http://)
  2. Internet address of the server(e.g., www.google.com)
  3. resource on the server
* ~~URN(Uniform Resource Name)~~

## HTTP Message
* **request**: client -> server
* **response**: server -> client
These are only two types of HTTP messages.
### Message Structure
1. **Start line** </br>
  This indicates what to do for a request or what happened for a response.
    * Request line
    * Response line
2. **Header fields** </br>
  Zero more more header fields follow the start line.</br>
  Each header field consists of a name and a value, separated by `:`. </br>
  The headers end with a blank line.
3. **Body** </br>
  Body is optional and can contain any kind of data.</br>
### Methods
|Method|Description|Message body?
|------|-----------|-------------
|GET|Get a document from the server|No
|HEAD|Get just the headers for a document from the server|No
|POST|Send data to the server for processing|Yes
|PUT|Store the body of the request on the server|Yes
|TRACE|Trace the message through proxy servers to the server|No
|OPTIONS|Determine what methods can operate on a server|No
|DELETE|Remove a document from the server|No
### Status Code
|Overall range|Defined range|Category
|-------------|-------------|--------
|100-199|100-101|Informational
|200-299|200-206|Successful
|300-399|300-305|Redirection
|400-499|400-415|Client error
|500-599|500-505|Server error

## Connections
HTTP network protocol stack
* **HTTP**: Application layer
* **TCP(Transmission Control Protocol)**: Transport layer
* **IP(Internet Protocol suite)**: Network layer
* **Network-specific link interface**: Data link layer
* **Physical network hardware**: Physical layer

In networking terms, the HTTP protocol is layered over TCP. </br>
HTTP uses TCP to transport message data. Likewise, TCP is layered over IP.
### TCP/IP
TCP/IP hides the features and foibles of individual networks and hardware, letting computers and networks of any type talk together.</br>
TCP/IP provides:
* Error-free data transportation
* In-order delivery(data will always arrive in the order in which it was sent)
* Unsegmented data stream(can dribble out in any size at any time)

In TCP, you need the IP address of the server and the TCP port number associated with the specific software program running on the server.
* IP address: e.g., `127.0.0.1`
* hostname: a human-friendly alias for an IP address

Hostnames can easily be converted into IP address through a facility called the **Domain Name Service(DNS)**. </br>
Here are the steps:
1. The browser extracts the server's hostname from the URL.
2. The browser converts the server's hostname into the server's IP address.
3. The browser extracts the port number (if any) from the URL.
4. The browser establishes a TCP connection with the web server.
5. The browser sends an HTTP request message to the server.
6. The server sends an HTTP response back to the browser.
7. The connection is closed, and the browser displays the document.

## Architectural Components of the Web
* **Proxies**: HTTP intermediaries that sit between clients and servers.
* **Caches**: HTTP storehouses that keep copies of popular web pages close to clients
* **Gateways**: Special web servers that connect to other applications
* **Tunnels**: Special proxies that blindly forward HTTP communications
* **Agents**: Semi-intelligent web clients that make automated HTTP requests