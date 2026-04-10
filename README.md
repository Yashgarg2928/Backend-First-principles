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

1. PUT : Is a request method.
2. /api/users/12345 : This is the source.
3. HTTP/1.1 : This is the HTTP version we are using 
4. HOST : This is our domain (frontend domain)
5. Then we have headers which conatines meta data about the request.
6. Then we have blank line which identify that headers and been ended
7. Then we have Body which containe data we want so send through this request.

**Use of Headers**
They are the meta data or address of the recipent in simple words it gives a quick way to see address of recipent.

**Request Headers**
1. User-Agent : It identifies which kind of clinte is that browser, postmen etc
2. Authorization : Send credential for authorization
3. Cookie
4. Accept : tells type of data.

**General Headers**
It has some information about the request or response message.
1. Data
2. Cache-control
3. Connection

**Reprenatation Header**
Info about the body of the message
1. Content-Type
2. Content-Length
3. Content-Encoding
4. ETag

**Security Headers**
Used the enhace the security of the request and message. By controlling things like encoding or cookie loading.
1. Strict-Transport-Security(HSTS)
2. Content-Security-POlicy
3. X-Frame-Options
4. X-content-Type-Options
5. Set-Cookie


**HTTP Methods**
Method defines the intent of an action 
1. GET : Used to get any data from the server.
2. POST : Used to send data to the server.
3. PUT: Used to update data but in this any data which comes should completly replace the data.
4. PATCH: This is used when we want to append data.
5. DELETE : This is used when we want to delete the data.


**Idempotent vs Non-idempotent**
Idempoyent: These are the methods that give same response each time. 
1. GET: Always get same kind of response
2. PUT 
3. DELETE

