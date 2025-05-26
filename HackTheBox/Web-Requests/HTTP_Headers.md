## HTTP Headers ([HTB](https://academy.hackthebox.com/module/35/section/223))

-   Headers can have one or multiple values, appended after the header name and separated by a colon. We can divide headers into the following categories:

    -   General Headers
    -   Entity Headers
    -   Request Headers
    -   Response Headers
    -   Security Headers

### General Headers

-   General headers are used in both HTTP requests and responses.
- They are contextual and are used to describe the message rather than its contents.

-   ![general](Screenshot%202025-05-25%20153946.png)

### Entity Headers

-   Entity Headers can be common to both the request and response.
-   These headers are used to describe the content (entity) transferred by a message. They are usually found in responses and POST or PUT requests.
-   ![entity](Screenshot%202025-05-25%20154101.png)

### Request Headers

- The client sends Request Headers in an HTTP transaction.
- These headers are used in an HTTP request and do not relate to the content of the message.
- The following headers are commonly seen in HTTP requests.
- ![request](Screenshot%202025-05-25%20155626.png)

### Response Headers

- Response Headers can be used in an HTTP response and do not relate to the content.
- Certain response headers such as Age, Location, and Server are used to provide more context about the response. 
- The following headers are commonly seen in HTTP responses.
- ![response](Screenshot%202025-05-25%20155830.png)

### Security Headers

- Finally, we have Security Headers.
- With the increase in the variety of browsers and web-based attacks, defining certain headers that enhanced security was necessary.
- HTTP Security headers are a class of response headers used to specify certain rules and policies to be followed by the browser while accessing the website.
- ![security](Screenshot%202025-05-25%20160121.png)

### cURL

- If we were only interested in seeing the response headers, then we can use the -I flag to send a HEAD request and only display the response headers. Furthermore, we can use the -i flag to display both the headers and the response body (e.g. HTML code)

- ![-i](Screenshot%202025-05-25%20160817.png)

- In addition to viewing headers, cURL also allows us to set request headers with the -H flag, as we will see in a later section. Some headers, like the User-Agent or Cookie headers, have their own flags. For example, we can use the -A to set our User-Agent, as follows: `curl https://www.inlanefreight.com -A 'Mozilla/5.0'`

### Browser DevTools

- Finally, let's see how we can preview the HTTP headers using the browser devtools. Just as we did in the previous section, we can go to the Network tab to view the different requests made by the page. We can click on any of the requests to view its details: 

- ![network-tab](https://academy.hackthebox.com/storage/modules/35/devtools_network_requests_details.jpg)

- In the first Headers tab, we see both the HTTP request and HTTP response headers.
- The devtools automatically arrange the headers into sections, but we can click on the Raw button to view their details in their raw format.
- Furthermore, we can check the Cookies tab to see any cookies used by the request, as discussed in an upcoming section.

