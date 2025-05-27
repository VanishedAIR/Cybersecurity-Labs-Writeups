## Hypertext Transfer Protocol Secure (HTTPS) ([HTB](https://academy.hackthebox.com/module/35/section/228))

-   One significant drawbacks of HTTP is that all data is transferred in clear-text, meaning anyone between the source and destination can perform a Man-in-the-middle (MiTM) attack to view the transferred data
-   To counter this, HTTPS (HTTP secure) protocol was created, where all communications are transferred in an encrypted format, so even if a 3rd party intercept the request, they would not be able to extract the data out of it

### HTTPS Overview

-   The following is a HTTP login request showing how easy it is to view credentials in clear-text

![HTTP login request](https://academy.hackthebox.com/storage/modules/35/https_clear.png)

-   On the other hand, this is how an HTTPS login request looks like

![HTTPS login request](https://academy.hackthebox.com/storage/modules/35/https_google_enc.png)

-   the data is transferred as a single encrypted stream, which makes it very difficult for anyone to capture information such as credentials or any other sensitive data

-   Websites that enforce HTTPS can be identified through https:// in their URL as well as the lock icon in the address bar of the web browser

### HTTPS Flow

![HTTPS operations](https://academy.hackthebox.com/storage/modules/35/HTTPS_Flow.png)

-   If we type http:// instead of https:// to visit a website that enforces HTTPS, the browser attempts to resolve the domain and redirects the user to the webserver hosting the target website

-   A request is sent to port 80 first, which is the unencrypted HTTP protocol. The server detects this and redirects the client to secure HTTPS port 443 instead

-   This is done via the 301 Moved Permanently response code, which we will discuss in an upcoming section

-   The client (web browser) sends a "client hello" packet, giving information about itself. After this, the server replies with "server hello", followed by a key exchange to exchange SSL certificates
    -   key exchange: Key exchange (also key establishment) is a method in cryptography by which cryptographic keys are exchanged between two parties, allowing use of a cryptographic algorithm.
-   After this, an encrypted handshake is initiated to confirm whether the encryption and transfer are working correctly.
    -   During the course of a TLS handshake, the client and server together will do the following:
        -   Specify which version of TLS (TLS 1.0, 1.2, 1.3, etc.) they will use
        -   Decide on which cipher suites they will use
        -   Authenticate the identity of the server via the server’s public key and the SSL certificate authority’s digital signature
        -   Generate session keys in order to use symmetric encryption after the handshake is complete
-   Once the handshake completes successfully, normal HTTP communication is continued, which is encrypted after that
-   Notes: Depending on the circumstances, an attacker may be able to perform an HTTP downgrade attack, which downgrades HTTPS communication to HTTP, making the data transferred in clear-text. This is done by setting up a Man-In-The-Middle (MITM) proxy to transfer all traffic through the attacker's host without the user's knowledge. However, most modern browsers, servers, and web applications protect against this attack

### cURL for HTTPS

-   cURL should automatically handle all HTTPS communication standards and perform a secure handshake and then encrypt and decrypt data automatically
-   if we ever contact a website with an invalid SSL certificate or an outdated one, then cURL by default would not proceed with the communication to protect against MITM attack

-   `curl https://inlanefreight.com` => `curl: (60) SSL certificate problem: Invalid certificate chain`

-   Modern web browsers would do the same, warning the user against visiting a website with an invalid SSL certificate.

-   applications may not yet have implemented a valid SSL certificate. To skip the certificate check with cURL, we can use the -k flag

-   `curl -k https://inlanefreight.com` => `<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN"><html><head>...`
