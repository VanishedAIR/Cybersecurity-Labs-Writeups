## HTTP Requests and Responses ([HTB](https://academy.hackthebox.com/module/35/section/220))

### Task Summary:

-   Use `curl [ip-address] -v` to see the version of Apache running

### Summary:

-   HTTP communications mainly consist of an HTTP request and an HTTP response
-   HTTP request is made by the client (e.g. cURL/browser), and is processed by the server (e.g. web server)
-   The requests contain all of the details we require from the server, including the resource (e.g. URL, path, parameters), any request data, headers or options we specify
-   Once the server receives the HTTP request, it processes it and responds by sending the HTTP response, which contains the response code

### HTTP Request

-   ![http-req](https://academy.hackthebox.com/storage/modules/35/raw_request.png)
-   The image shows an HTTP GET request to the URL: http://inlanefreight.com/users/login.html
-   The first line of any HTTP request contains 3 main fields.
-   In the example: GET /users/login.html HTTP/1.1

    -   Method: GET -> The HTTP method or verb, specifies the type of action to perform
    -   Path: /users/login.html -> The path to the resource being accessed. This field can also be suffixed with a query string (e.g. ?username=user)
    -   Version: HTTP/1.1 -> The third and final field is used to denote the HTTP version.

-   The next set of lines contain HTTP header value pairs, like Host, User-Agent, Cookie, and many other possible headers.
-   These headers are used to specify various attributes of a request. The headers are terminated with a new line, which is necessary for the server to validate the request.
-   Finally, a request may end with the request body and data.

**Note:** HTTP version 1.X sends requests as clear-text, and uses a new-line character to separate different fields and different requests. HTTP version 2.X, on the other hand, sends requests as binary data in a dictionary form.

### HTTP Response

-   Once the server processes our request, it sends its response. The following is an example HTTP response:
-   ![http-response](https://academy.hackthebox.com/storage/modules/35/raw_response.png)
-   The first line of an HTTP response contains two fields separated by spaces. The first being the HTTP version (e.g. HTTP/1.1), and the second denotes the HTTP response code (e.g. 200 OK).
-   Response codes are used to determine the request's status.
-   After the first line, the response lists its headers, similar to an HTTP request.
-   The response may end with a response body, which is separated by a new line after the headers.
-   The response body is usually defined as HTML code. However, it can also respond with other code types such as JSON, website resources such as images, style sheets or scripts, or even a document such as a PDF document hosted on the webserver.

### cURL

-   cURL also allows us to preview the full HTTP request and the full HTTP response, which can become very handy when performing web penetration tests or writing exploits.
-   To view the full HTTP request and response, we can simply add the -v verbose flag to our earlier commands, and it should print both the request and response: `curl inlanefreight.com -v`
-   We get the full HTTP request and response. The request simply sent GET / HTTP/1.1 along with the Host, User-Agent and Accept headers.
-   In return, the HTTP response contained the HTTP/1.1 401 Unauthorized, which indicates that we do not have access over the requested resource
-   Similar to the request, the response also contained several headers sent by the server, including Date, Content-Length, and Content-Type
-   The response contained the response body in HTML, which is the same one we received earlier when using cURL without the -v flag.

### Browser DevTools

-   Whenever we visit any website or access any web application, our browser sends multiple web requests and handles multiple HTTP responses to render the final view we see in the browser window. To open the browser devtools in either Chrome or Firefox, we can click [CTRL+SHIFT+I] or simply click [F12]. The devtools contain multiple tabs, each of which has its own use. We will mostly be focusing on the Network tab in this module, as it is responsible for web requests.

![network](https://academy.hackthebox.com/storage/modules/35/devtools_network_requests.jpg)

-   The devtools show us at a glance the response status (i.e. response code), the request method used (GET), the requested resource (i.e. URL/domain), along with the requested path. Furthermore, we can use Filter URLs to search for a specific request, in case the website loads too many to go through.
