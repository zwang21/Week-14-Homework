## Week 14 Homework: Web Development

Overview
In this homework, we will review the many of the concepts and tools covered in the Web Development unit. If needed, refer to the  reference sheets provided to you.

### HTTP Requests and Responses

Answer the following questions about the HTTP request and response process.

1. What type of architecture does the HTTP request and response process occur in?

	`Client-Server Architecture`
 
1. What are the different parts of an HTTP request?

	Below are the various HTTP requests. 

| HTTP Method | Description                                                  |
| ----------- | ------------------------------------------------------------ |
| GET         | The GET method requests data *from* a server. Requests using GET should only retrieve data. |
| HEAD        | The HEAD method is identical to GET except that the server does not send the response body.|
| POST        | The POST method sends data *to* the specified resource, often changing or updating the server. |
| PUT         | The PUT method replaces or updates resources with the request payload. |
| DELETE      | The DELETE method deletes the specified resource from the server            |
| CONNECT     | The CONNECT method establishes a tunnel to the server. |
| OPTIONS     | The OPTIONS method describes the communication options for the specified resource. |

	 
1. Which part of an HTTP request is optional?
 
	The `request body` is optional.
 
1. What are the three parts of an HTTP response?
 
	`Status line, Headers, Response body` 
 
1. Which number class of status codes represents errors?
	- 400 codes indicate client errors
	- 500 codes indicate server errors

1. What are the two most common request methods that a security professional will encounter?

	`GET` and `POST` 
 
1. Which type of HTTP request method is used for sending data?

	`POST` 
 
1. Which part of an HTTP request contains the data being sent to the server?
 
	`Request body`
 
1. In which part of an HTTP response does the browser receive the web code to generate and style a web page?

	The `Response body` contains the actual HTML web codes requested by the client.
	
### Using curl

Answer the following questions about `curl`:


1. What are the advantages of using `curl` over the browser?

	`curl` does not require user interaction

1. Which `curl` option is used to change the request method?

	`--request`

1. Which `curl` option is used to set request headers?

	`-v`

1. Which `curl` option is used to view the response header?

	`-I`

1. Which request method might an attacker use to figure out which HTTP requests an HTTP server will accept?

	`OPTIONS`

### Sessions and Cookies

Recall that HTTP servers need to be able to recognize clients from one another. They do this through sessions and cookies.

Answer the following questions about sessions and cookies:

1. Which response header sends a cookie to the client?
```
HTTP/1.1 200 OK
Content-type: text/html
Set-Cookie: cart=Bob
```

```
Set-Cookie: cart=Bob
```

1. Which request header will continue the client's session?
```
GET /cart HTTP/1.1
Host: www.example.org
Cookie: cart=Bob
```
```
Cookie: cart=Bob
```

### Example HTTP Requests and Responses

Look through the following example HTTP request and response and answer the following questions:

### HTTP Request

```
POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password
```
1. What is the request method?

	`POST`

1. Which header expresses the client's preference for an encrypted response?

	`Upgrade-Insecure-Requests: 1`

1. Does the request have a user session associated with it?

	Not yet

1. What kind of data is being sent from this request body?

	Login credential was sent.
```
	username=Barbara
	password=password
```
### HTTP Response

```
HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]
```

1. What is the response status code?

	200

1. What web server is handling this HTTP response?
 
	Apache

1. Does this response have a user session associated to it?
 
 	Yes, `Set-Cookie: SessionID=5`

1. What kind of content is likely to be in the [page content] response body?
 
	Account log in interface.

1. If your class covered security headers, what security request headers have been included?

	Authorization header

### Monoliths and Microservices

Answer the following questions about monoliths and microservices:

1. What are the individual components of microservices called?

	`Service`

1. What is a service that writes to a database and communicates to other services?

	`API`: application programming interface

1. What type of underlying technology allows for microservices to become scalable and have redundancy?

	`Docker container`

### Deploying and Testing a Container Set

Answer the following questions about multi-container deployment:

1. What tool can be used to deploy multiple containers at once?

	`docker-compose`

1. What kind of file format is required for us to deploy a container set?

	`Docker Compose YAML files`

### Databases

1. Which type of SQL query would we use to see all of the information within a table called customers?

	`SELECT * FROM customers;`

1. Which type of SQL query would we use to enter new data into a table? (You don't need a full query, just the first part of the statement.)

	`INSERT INTO customers (field1, field 2, ...) VALUES ('a', 'b', ...);`

1. Why would we never run `DELETE FROM <table-name>;` by itself?

	Because this `sql` query will delete everything in the table.
