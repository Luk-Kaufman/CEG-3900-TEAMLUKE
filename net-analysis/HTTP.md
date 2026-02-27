# HTTP Notes

Hypertext Transfer Protocol (HTTP) is an application-layer protocol used for transmitting data over the web. HTTP defines how messages are formatted and transmitted between clients and servers, as well as how servers should respond to these kinds of requests. When you put a URL into a browser, HTTP is what allows your browser to request a resource (website, image, etc) from the server and recieve that response. HTTP is stateless, meaning each request is seperate and does not remember info about previous requests unless additional mechanisms are used such as cookies.

---

## Why HTTP Is Important

HTTP is important because it
- allows communication between browsers and servers
- creates the foundation of the www (worldwide web)
- works across different platforms/devices
- allows standard communication via request and response
- helps secure communication when combined with any sort of encryption, which is HTTPS

---

## Concepts

### Client Server Model

- A client sends a request
- A server processes said request and sends back a response
Communication repeats this process

### HTTP Methods

- `GET` – Retrieve data from a server
- `POST` – Send data to a server
- `PUT` – Update existing data
- `DELETE` – Remove data
- `PATCH` – Partially update data
- `HEAD` – Retrieve headers only

### Request Structure

- Request Line - method, URL, HTTP version
- Headers - metadata like content type, authorization
- Body - optional data sent to server, mainly with `POST`/`PUT`

### Response Structure

- Status Line - HTTP version + status code
- Status Code
- Headers - metadata about response
- Body - the actual content

### Status Codes

- 1xx – Informational
- 2xx – Success (200 OK)
- 3xx – Redirection (301 Moved Permanently)
- 4xx – Client errors (404 Not Found)
- 5xx – Server errors (500 Internal Server Error)

### Statelessness

- Each request is seperate
- No built-in memory of past requests
- Sessions and cookies are used to maintain state

### HTTP vs HTTPS

- HTTP - Data sent in plain text
- HTTPS is encrypted using SSL/TLS
- HTTPS protects sensitive data such as passwords
