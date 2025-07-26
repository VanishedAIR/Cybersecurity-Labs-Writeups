## Putting It All Together ([TryHackMe - YouTube](https://www.youtube.com/watch?v=Aa_FAA3v22g&list=PL0iJrrpaWpyU5OQnrSis1Qjt_UYjkvCKd&index=4))

### Task Summary:

- Combine knowledge from every module to drag and drop tiles into the correct order of how a request to a website works. Request in your browser -> Check local cache for IP address to see if we have made this request before -> Check your recursive DNS server for address if not found locally -> Then will query root server to find authoritative DNS server -> authoritative DNS server advises the IP address for the website -> Request passes through a WAF (web application firewall) -> Request passes through a load balancer -> connect to webserver on port 80 or 443 -> web server receives the GET request -> Web Application talks to DB for dynamic content or authentication -> Your browser renders the HTML into a viewable website 

### Summary:

#### Putting It All Together

-   When you request a website, your computer needs to know the server's IP address it needs to talk to; for this, it uses DNS.
-   Your computer then talks to the web server using a special set of commands called the HTTP protocol; the webserver then returns HTML, JavaScript, CSS, Images, etc., which your browser then uses to correctly format and display the website to you.

![summarized](Screenshot%202025-05-24%20120819.png)

-   There are also a few other components that help the web run more efficiently, and provide extra features

#### Other Components

-   When a website's traffic starts getting quite large or is running an application that needs to have high availability, one web server might no longer do the job.
-   Load balancers provide two main features, ensuring high traffic websites can handle the load and providing a failover if a server becomes unresponsive.

-   When you request a website with a load balancer, the load balancer will receive your request first and then forward it to one of the multiple servers behind it.
-   The load balancer uses different algorithms to help it decide which server is best to deal with the request.
-   A couple of examples of these algorithms are round-robin, which sends it to each server in turn, or weighted, which checks how many requests a server is currently dealing with and sends it to the least busy server.

-Load balancers also perform periodic checks with each server to ensure they are running correctly; this is called a health check.

-   If a server doesn't respond appropriately or doesn't respond, the load balancer will stop sending traffic until it responds appropriately again.

![load-balancer](https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/829e340231cd8aa9f5ed2fa5c464ea80.svg)

-   CDN (Content Delivery Networks)

    -   A CDN can be an excellent resource for cutting down traffic to a busy website.
    -   It allows you to host static files from your website, such as JavaScript, CSS, Images, Videos, and host them across thousands of servers all over the world.
    -   When a user requests one of the hosted files, the CDN works out where the nearest server is physically located and sends the request there instead of potentially the other side of the world.

-   Databases

    -   Often websites will need a way of storing information for their users.
    -   Webservers can communicate with databases to store and recall data from them.
    -   Databases can range from just a simple plain text file up to complex clusters of multiple servers providing speed and resilience
    -   Some common databases: MySQL, MSSQL, MongoDB, Postgres, and more; each has its specific features.

-   WAF (Web Application Firewall)
    -   A WAF sits between your web request and the web server; its primary purpose is to protect the webserver from hacking or denial of service attacks.
    -   It analyses the web requests for common attack techniques, whether the request is from a real browser rather than a bot.
    -   It also checks if an excessive amount of web requests are being sent by utilizing something called rate limiting, which will only allow a certain amount of requests from an IP per second.
    -   If a request is deemed a potential attack, it will be dropped and never sent to the webserver.

![WAF](https://tryhackme-images.s3.amazonaws.com/user-uploads/5c549500924ec576f953d9fc/room-content/24cb6468b4e51e8d8bbe7872e96a22b3.svg)

#### How Web Servers Work

-   What is a Web Server?

    -   A web server is software that listens for incoming connections and utilizes the HTTP protocol to deliver web content to clients
    -   Common web server software includes Apache, Nginx, IIS, and NodeJS
    -   Web servers deliver files from a designated root directory defined in the software settings
    -   For example, Nginx and Apache use the default location of `/var/www/html` in Linux systems, while IIS uses `C:\inetpub\wwwroot` for Windows systems
    -   When you request a file like http://www.example.com/picture.jpg, the server sends the file `/var/www/html/picture.jpg` from its local hard drive

-   Virtual Hosts:

    -   Web servers can host multiple websites with different domain names using virtual hosts
    -   The web server checks the requested hostname in the HTTP headers and matches it against its virtual hosts configuration files
    -   If a match is found, the correct website is provided; if not, the default website is served
    -   Virtual hosts can have their root directories mapped to different locations on the hard drive
    -   For example, one.com can be mapped to `/var/www/website_one`, and two.com to `/var/www/website_two`
    -   There's no limit to the number of different websites you can host on a single web server

-   Static vs Dynamic Content:

    -   Static content never changes - includes pictures, JavaScript, CSS, and HTML files that remain consistent
    -   These files are served directly from the webserver with no modifications
    -   Dynamic content changes based on different requests
    -   Examples include blog homepages that update with new entries or search pages that display different results
    -   These changes happen in the Backend using programming and scripting languages
    -   The Backend processes occur behind the scenes - you cannot view this code in the website's HTML source
    -   Everything you see in your browser is called the Frontend, which is the result of Backend processing

-   Scripting and Backend Languages:
    -   Backend languages make websites interactive for users
    -   Examples include PHP, Python, Ruby, NodeJS, Perl, and many others
    -   These languages can interact with databases, call external services, process user data, and more
    -   A basic PHP example: If you request http://example.com/index.php?name=adam with code `<html><body>Hello <?php echo $_GET["name"]; ?></body></html>`, it would output `<html><body>Hello adam</body></html>` to the client
    -   The client doesn't see any PHP code because it's processed on the Backend
    -   This interactivity introduces more security issues for web applications that haven't been created securely
