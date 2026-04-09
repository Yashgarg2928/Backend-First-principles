# Backend-First-principles

### What is a backend? And what is its need?
A backend server is essentially a central machine that has a connection to all the clients and services. Its work is to handle all the services related to data and business logic.

### Why not use frontend for backend logic?
Frontend works basically when we call a URL path, it sends a request to the reverse proxy, then that sends our frontend code to the  browser, and that code will be run in the browser. which has limited resources. It has a security issue, as anyone can change the frontend code in their browser. We can call APIs from different domains.

### HTTP 
It is the medium/protocol that we use to send and receive data between the server and the client. There are other protocols too, but HTTP is the most commonly used.

1. Stateless: This first idea of HTTP does not have any past data, which means each request must have all the required data each time. It is used as it is simple and can easily be scaled. As no session history needs to be stored between servers.
2. Client-server model: In this model, we always have a client and a server. In this, the client sends a request, and the server always sends a response. And HTTP states that the client always initiates the connection.

To send some kind of request or response, we need some kind of connection protocol, which we use is TCP.


**Versions of HTTP**:
* 1.0: In this, we needed to make a new connection for each request.
* 1.1: In this, they introduced a persistent connection by which we can send multiple requests in one connection only. And better caching and more.
* 2: It uses binary framing, which replaces TEXT and allows HRADER compression.
* 3: Works on UDP.


**Request Message**
```
PUT /api/users/12345 HTTP/1.1
Host: example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
AppLeWebKit/537.36 (KHTML, Like Gecko) Chrome/93.0.4577.82
Safari/537.36
Content-Type: application/json
Content-Length: 123
Authorization: Bearer
Accept: application/json
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Referer: https://example.com/dashboard
Cookie: sessionId=abc123xyz456; Lang=en-US
// a blank line here means, everything has been sent
"firstName": "John",
"lastName": "Doe",
"email": "john.doe@example.com"
"age": 30
```
