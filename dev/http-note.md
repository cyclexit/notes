# HTTP Note

## Index
* [MIME Type](#MIME-Type)
* [URI](#URI)
* [HTTP Message](#HTTP-Message)
  * [Message Structure](#Message-Structure)
  * [Methods](#Methods)
  * [Status Code](#Status-Code)

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
* `request`: client -> server
* `response`: server -> client
These are only two types of HTTP messages.
### Message Structure
1. Start line </br>
  This indicates what to do for a request or what happened for a response.
    * Request line
    * Response line
2. Header fields
  Zero more more header fields follow the start line.</br>
  Each header field consists of a name and a value, separated by `:`. </br>
  The headers end with a blank line.
3. Body
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