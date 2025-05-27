## HTTP ([HTB](https://academy.hackthebox.com/module/35/section/219))

### HyperText Transfer Protocol (HTTP)

-   An application-level protocol used to access the World Wide Web resources
-   Hypertext - stands for text containing links to other resources and text that the readers can easily interpret
-   HTTP communication consists of a client and a server, where the client requests the server for a resource. The server processes the request and returns the requested resource.
-   Default port for HTTP communication is port 80, thought this can be changed to any other port, depending on the web server configuration
-   We enter a Fully Qualified Domain Name (FQDN) as a Uniform Resource Locator (URL) to reach the desired website, like www.hackthebox.com

### URL

-   Resources over HTTP are accessed via a URL, which offers many more specification than simply specifying a website we want to visit.
-   Example URL: http://admin:password@inlanefreight.com:80/dashboard.php>login=true#status
    -   Scheme: http:// or https:// is used to identify the protocol being accessed by the client, and ends with a colon and a double slash
    -   User Info: admin:password@ is an optional component that contains the credentials (separated by a colon : ) used to authenticate to the host, and is separated from the host with an at sign (@)
    -   Host: inlanefreight.com signifies the resource location. This can be a hostname or an IP address
    -   Port: :80, the port, is separated from the Host by a colon. If no port is specified, http defaults to port 80 and https defaults to 443
    -   Path: /dashboard.php points to the resource being accessed, which can be a file or folder. If no path specified, server returns the default index (index.html)
    -   Query String: ?login=true starts with a question mark (?), and consists of a parameter (e.g. login) and a value (e.g. true). Multiple parameters can be separated by an ampersand (&)
    -   Fragments: #status processed by the browsers on the client-side to locate sections within the primary resource (e.g. a header or section on the page)
-   Not all components are required to access a resource. The main mandatory fields are the scheme and the host, without which the request would have no resource to request

### HTTP Flow

![HTTP Flow Diagram](https://academy.hackthebox.com/storage/modules/35/HTTP_Flow.png)

-   The first time a user enters the URL (inlanefreight.com) into the browser, it sends a request to a DNS (Domain Name System) server to resolve the domain and get its IP
-   The DNS server looks up the IP address for inlanefreight.com and returns it
-   All domain names need to be resolved this way, as a server can't communicate without an IP address
-   Once the browser gets the IP address linked to the requested domain, it sends a GET request to the default HTTP port (e.g. 80), asking for the root / path
-   Then, the web server receives the request and processes it. By default, servers are configured to return an index file when a request for / is received
-   In this case, the contents of index.html are read and returned by the web server as an HTTP response. The response also contains the status code (e.g. 200 OK), which indicates that the request was successfully processed
-   The web browser then renders the index.html contents and presents it to the user

### cURL

-   cURL (client URL) is a command-line tool and library that primarily supports HTTP along with many other protocols
-   This makes it a good candidate for scrips as well as automation, making it essential for sending various types of web requests from the command line, necessary for many types of web penetration tests
-   `$ curl inlanefreight.com`
-   cURL does not render the HTML/JS/CSS, rather prints it in raw format
-   As penetration testers, we are mainly interested in the request and response context, which usually becomes much faster and more convenient than a web browser
-   We may also use cURL to download a page or a file and output the content into a file using the -O flag
-   If we want to specify the output file name, we can use the -o flag and specify the name. Otherwise, we can use -O and cURL will use the remote file name, as follows
-   `curl -O inlanefreight.com/index.html` -> `ls` => index.html
-   the output was not printed this time but rather saved into index.html
-   cURL still printed some status while processing the request. We can silent the status with the -s flag
-   `curl -s -O inlanefreight.com/index.html`
-   use the -h flag to see what other options we may use with cURL
