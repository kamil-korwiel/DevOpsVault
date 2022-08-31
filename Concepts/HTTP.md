# HTTP
---
( HyperText Transfer Protocol ) - is an application-level protocol used to connect to Web servers on the Internet. The primary function of HTTP is to establish a connection with the server and send HTML pages back to the user's browser. It is also used to download data from the server either to the browser or to any requesting application that uses HTTP.

It was created for communication between browsers and web servers, but can be used for other purposes as well. HTTP is based on the classic client-server model, where the client initiates a connection by sending a request, then waits for a response. HTTP is a stateless protocol, meaning that the server does not store any data (state) between both requests. Although it is often based on the TCP/IP layer, it can also be used on the trustworthy transport layer, i.e. a protocol that does not silently lose messages, as is the case with UDP. RUDP, a trustworthy update of UDP, may be a suitable alternative.
[To learn more click here](https://developer.mozilla.org/pl/docs/Web/HTTP)
# Headers
---
**HTTP header** is a field of an HTTP request or response that passes additional context and metadata about the request or response.
For example, a request message can use headers to indicate it's preferred media formats, while a response can use header to indicate the media format of the returned body. Headers are case-insensitive, begin at the start of a line and are immediately followed by a `':'` and a header-dependent value.

-   [General headers](https://developer.mozilla.org/en-US/docs/Glossary/General_header), like [`Via`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Via), apply to the whole message.
-   [Response headers](https://developer.mozilla.org/en-US/docs/Glossary/Response_header), like [`Vary`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Vary) and [`Accept-Ranges`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Accept-Ranges), give additional information about the server which doesn't fit in the status line.
-   [Representation headers](https://developer.mozilla.org/en-US/docs/Glossary/Representation_header) like [`Content-Type`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Type) that describe the original format of the message data and any encoding applied (only present if the message has a body).

https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages read more

![Example of headers in an HTTP response](https://developer.mozilla.org/en-US/docs/Web/HTTP/Messages/http_response_headers3.png)

To show headers of web site  use this command :
``` bash
curl -I https://example.site.com 
```

#  Request methods 
---
[`GET`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/GET) - The `GET` method requests a representation of the specified resource. Requests using `GET` should only retrieve data.

[`HEAD`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/HEAD) - The `HEAD` method asks for a response identical to a `GET` request, but without the response body.

[`POST`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/POST) - The `POST` method submits an entity to the specified resource, often causing a change in state or side effects on the server.

[`PUT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PUT) - The `PUT` method replaces all current representations of the target resource with the request payload.

[`DELETE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/DELETE) - The `DELETE` method deletes the specified resource.

[`CONNECT`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/CONNECT) - The `CONNECT` method establishes a tunnel to the server identified by the target resource.

[`OPTIONS`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/OPTIONS) - The `OPTIONS` method describes the communication options for the target resource.

[`TRACE`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/TRACE) - The `TRACE` method performs a message loop-back test along the path to the target resource.

[`PATCH`](https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods/PATCH) - The `PATCH` method applies partial modifications to a resource.

# Status code
---
HTTP response status codes indicate whether a specific [HTTP](https://developer.mozilla.org/en-US/docs/Web/HTTP) request has been successfully completed. Responses are grouped in five classes:
1.  Informational responses (`100`–`199`)
2.  Successful responses (`200`–`299`)
3.  Redirection messages (`300`–`399`)
4.  Client error responses (`400`–`499`)
5.  Server error responses (`500`–`599`)

**Status code**                                                               |**Meaning**                           
------------------------------------------------------------------------------|--------------------------------------
1xx Informational|                                      
100                                                                           |Continue                              
101                                                                           |Switching protocols                   
102                                                                           |Processing                            
103                                                                           |Early Hints                           
                                                                              |                                      
2xx Succesful    |                                      
200                                                                           |OK                                    
201                                                                           |Created                               
202                                                                           |Accepted                              
203                                                                           |Non-Authoritative Information         
204                                                                           |No Content                            
205                                                                           |Reset Content                         
206                                                                           |Partial Content                       
207                                                                           |Multi-Status                          
208                                                                           |Already Reported                      
226                                                                           |IM Used                               
                                                                              |                                      
3xx Redirection  |                                      
300                                                                           |Multiple Choices                      
301                                                                           |Moved Permanently                     
302                                                                           |Found (Previously "Moved Temporarily")
303                                                                           |See Other                             
304                                                                           |Not Modified                          
305                                                                           |Use Proxy                             
306                                                                           |Switch Proxy                          
307                                                                           |Temporary Redirect                    
308                                                                           |Permanent Redirect                    
                                                                              |                                      
4xx Client Error |                                      
400                                                                           |Bad Request                           
401                                                                           |Unauthorized                          
402                                                                           |Payment Required                      
403                                                                           |Forbidden                             
404                                                                           |Not Found                             
405                                                                           |Method Not Allowed                    
406                                                                           |Not Acceptable                        
407                                                                           |Proxy Authentication Required         
408                                                                           |Request Timeout                       
409                                                                           |Conflict                              
410                                                                           |Gone                                  
411                                                                           |Length Required                       
412                                                                           |Precondition Failed                   
413                                                                           |Payload Too Large                     
414                                                                           |URI Too Long                          
415                                                                           |Unsupported Media Type                
416                                                                           |Range Not Satisfiable                 
417                                                                           |Expectation Failed                    
418                                                                           |I'm a Teapot                          
421                                                                           |Misdirected Request                   
422                                                                           |Unprocessable Entity                  
423                                                                           |Locked                                
424                                                                           |Failed Dependency                     
425                                                                           |Too Early                             
426                                                                           |Upgrade Required                      
428                                                                           |Precondition Required                 
429                                                                           |Too Many Requests                     
431                                                                           |Request Header Fields Too Large       
451                                                                           |Unavailable For Legal Reasons         
                                                                              |                                      
5xx Server Error |                                      
500                                                                           |Internal Server Error                 
501                                                                           |Not Implemented                       
502                                                                           |Bad Gateway                           
503                                                                           |Service Unavailable                   
504                                                                           |Gateway Timeout                       
505                                                                           |HTTP Version Not Supported            
506                                                                           |Variant Also Negotiates               
507                                                                           |Insufficient Storage                  
508                                                                           |Loop Detected                         
510                                                                           |Not Extended                          
511                                                                           |Network Authentication Required

[Read more about status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

