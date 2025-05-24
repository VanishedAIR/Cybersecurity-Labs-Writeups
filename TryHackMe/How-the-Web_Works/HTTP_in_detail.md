## HTTP in Detail ([TryHackMe - YouTube](https://www.youtube.com/watch?v=XZyapIKV3Rw&list=PL0iJrrpaWpyU5OQnrSis1Qjt_UYjkvCKd&index=2))

### Task Summary:

-   First simulation shows how different status codes might look like, ex: 403 - Forbidden, 404 - Error Not Found, 503 - Service Unavailable
- An emulator for making demo HTTP requests. Example: sending a GET request to http://tryhackme.com/room sends the `GET /room HTTP/1.1`
`Host: tryhackme.com`
`User-Agent: Mozilla/5.0 Firefox/87.0`

with a response being

`HTTP/1.1 200 Ok`
`Server: nginx/1.15.8`
`Fri, 23 May 2025 22:50:03 PST`
`Content-Type: text/html; charset=utf-8`
`Content-Length: 233`
`Last-Modified: Fri, 23 May 2025 22:50:03 PST`
`Bunch of HTML code <here>`

Another get request to blog with id = 1, DELETE request to /user/1, PUT request to /user/2 with username param set to admin, POST the username of thm and a password of letmein to /login
 
### Summary:

#### What is HTTP(S)?

-   HTTP (Hypertext Transfer Protocol) is the protocol that specifies how a web browser and a web server communicate
-   HTTPS is the secure version of HTTP.
-   HTTPS data is encrypted so it not only stops people from seeing the data you are receiving and sending, but it also gives you assurances that you’re talking to the correct web server and not something impersonating it.

#### Requests & Responses

-   If you’ve used the internet, you’ve used a URL before.
-   A URL is predominantly an instruction on how to access a resource on the internet.

-   http://user:password@tryhackme.com/80/view-room?id=1#task3

    -   “http” | This is the scheme. This instructs on what protocol to use for accessing the resource such as HTTP, HTTPS, or FTP (File Transfer Protocol).
    -   “user:password” | This is the user. Some services require authentication to log in, you can put a username and password into the URL to log in.
    -   “tryhackme.com” | This is the host. This is the domain name or IP address of the server you wish to access.
    -   “80” | This is the port that you are going to connect to, usually 80 for HTTP and 443 for HTTPS, but this can be hosted on any port between 1–65535.
    -   “view-room” | This is the file name or location of the resource you are trying to access.
    -   “?id=100” | This is the query string. It is extra bits of information that can be sent to the requested path. For example, /blog?id=1 would tell the blog path that you wish to receive the blog article with the id of 1.
    -   “#task3” | This is a fragment which is a reference to a location on the actual page requested. This is commonly used for pages with long content and can have a certain part of the page directly linked to it, so it is viewable to the user as soon as they access the page.

Note: It’s possible to make a request to a web server with just one line “GET / HTTP/1.1”.
![HTTP-One-Line](Screenshot%202025-05-23%20212226.png)

-   For much richer web experience, you'll need to send other data as well.
-   This other data is sent in what is called headers, where headers contain extra information to give the web server you're communicating with.

-   Example Request:

    `1. GET / HTTP/1.1`
    `2. Host: tryhackme.com`
    `3. User-Agent: Mozilla/5.0 Firefox/87.0`
    `4. Referer: https://tryhackme.com/`
    `5. `

    -   Line 1: This request is sending the GET method ( more on this in the HTTP Methods task ), requesting the home page with / and telling the web server we are using HTTP protocol version 1.1.

    -   Line 2: We tell the web server we want the website tryhackme.com

    -   Line 3: We tell the web server we are using the Firefox version 87 Browser

    -   Line 4: We are telling the web server that the web page that referred us to this one is https://tryhackme.com

    -   Line 5: HTTP requests always end with a blank line to inform the web server that the request has finished.

-   Example Response

    `1. HTTP/1.1 200 OK`
    `2. Server: nginx/1.15.8`
    `3. Date: Fri, 09 Apr 2021 13:34:03 GMT`
    `4. Content-Type: text/html`
    `5. Content-Length: 98`
    `6. `
    `7. <html>`
    `8. <head>`
    `9.      <title>TryHackMe</title>`
    `10. </head>`
    `11. <body>`
    `12.     Welcome To TryHackMe.com`
    `13. </body>`
    `14. </html>`

    -   Line 1: HTTP 1.1 is the version of the HTTP protocol the server is using and then followed by the HTTP Status Code in this case “200 OK” which tells us the request has been completed successfully.

    -   Line 2: This tells us the web server software and version number.

    -   Line 3: The current date, time and timezone of the web server.

    -   Line 4: The Content-Type header tells the client what sort of information is going to be sent, such as HTML, images, videos, pdf, and XML.

    -   Line 5: Content-Length tells the client how long the response is, this way we can confirm no data is missing.

    -   Line 6: The HTTP response contains a blank line to confirm the end of the HTTP response.

    -   Lines 7–14: The information that has been requested, in this instance the homepage.

#### HTTP Methods

-   GET Request: This is used for getting information from a web server.
-   POST Request: This is used for submitting data to the web server and potentially creating new records.
-   PUT Request: This is used for submitting data to a web server to update information.
-   DELETE Request: This is used for deleting information/records from a web server.

#### HTTP Status Codes

-   HTTP Status Codes

-   When a HTTP server responds, the first line always contains a status code informing the client of the outcome of their request and also potentially how to handle it. These status codes can be broken down into 5 different ranges:

    -   100–199 (Information Response): These are sent to tell the client the first part of their request has been accepted and they should continue sending the rest of their request. These codes are no longer very common.
    -   200–299 (Success): This range of status codes is used to tell the client their request was successful.
    -   300–399 (Redirection): These are used to redirect the client’s request to another resource. This can be either to a different webpage or a different website altogether.
    -   400–499 (Client Errors): Used to inform the client that there was an error with their request.
    -   500–599 (Server Errors): This is reserved for errors happening on the server side and usually indicates quite a major problem with the server handling the request.

Other specific status codes:
![200-403](Screenshot%202025-05-23%20222058.png)
![403-503](Screenshot%202025-05-23%20222233.png)

#### Headers

-   Headers are additional bits of data you can send to the web server when making requests. Although no headers are strictly required when making a HTTP request, you’ll find it difficult to view a website properly.

-   Common Request Headers
    -   Host: Some web servers host multiple websites so by providing the host headers you can tell it which one you require, otherwise you’ll just receive the default website for the server.
    -   User-Agent: This is your browser software and version number, telling the web server your browser software helps it format the website properly for your browser and also some elements of HTML, JavaScript and CSS are only available in certain browsers.
    -   Content-Length: When sending data to a web server such as in a form, the content length tells the web server how much data to expect in the web request. This way the server can ensure it isn’t missing any data.
    -   Accept-Encoding: Tells the web server what types of compression methods the browser supports so the data can be made smaller for transmitting over the internet.
    -   Cookie: Data sent to the server to help remember your information.

-   Common Response Headers
    -   Set-Cookie: Information to store which gets sent back to the web server on each request.
    -   Cache-Control: How long to store the content of the response in the browser’s cache before it requests it again.
    -   Content-Type: This tells the client what type of data is being returned, i.e., HTML, CSS, JavaScript, Images, PDF, Video, etc. Using the content-type header the browser then knows how to process the data.
    -   Content-Encoding: What method has been used to compress the data to make it smaller when sending it over the internet.

### Cookies
- They’re a small piece of data that is stored on your computer.
- Cookies are saved when you receive a “Set-Cookie” header from a web server.
- Then every further request you make, you’ll send the cookie data back to the web server.
- Because HTTP is stateless (doesn’t keep track of your previous requests), cookies can be used to remind the web server who you are, some personal settings for the website or whether you’ve been to the website before.
- They have other use cases, but are most commonly used for website authentication.
- The cookie value won't usually be a clear-text string where you can see the password, but a token (unique secret code that isn't humanly guessable)
![cookies](https://miro.medium.com/v2/resize:fit:4800/format:webp/0*NBG94KlrFp1uqpZ-)

