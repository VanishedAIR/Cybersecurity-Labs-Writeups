## DNS in Detail ([TryHackMe - YouTube](https://www.youtube.com/watch?v=jpTY1S5vs9k&list=PL0iJrrpaWpyU5OQnrSis1Qjt_UYjkvCKd&index=1))

### Task Summary:

- Searching up different information about websites, looking for things like CNAME, TXT, MX, A record of a website using `nslookup --type=CNAME shop.website.thm` for example

### Summary:

#### What is DNS?

-   DNS (Domain Name System) provides a simple way for us to communicate with devices on the internet without remembering complex numbers.
-   Every computer on the internet has its own IP address.
-   When you want to visit a website, it’s not exactly convenient to remember this complicated set of numbers, and that’s where DNS can help.
-   So instead of remembering 104.26.10.229, you can remember tryhackme.com instead.
    ![DNS](Screenshot%202025-05-23%20191806.png)

#### Domain Hierarchy

-   A TLD (Top Level Domain) is the most right hand part of a domain name.

    -   There are two types of TLD, gTLD (Generic TLD) and ccTLD (Country Code TLD).
    -   Example 1: A gTLD (such as .com / .org) would be for a specific purpose (such as commercial or an organization).
    -   Due to demand, new gTLDs are being used (e.g. .online / .club).
    -   Example 2: A ccTLD would be for country codes (such as .ar / .co.uk).

-   A Second-Level Domain is restricted to 63 characters, and can only use (a-z, 0–9) and hyphens.

    -   The maximum length of a domain name is 253 characters.
    -   Cannot start or end with hyphens or have consecutive hyphens

-   A subdomain sits on the left-hand side of the Second-Level Domain using a period to separate it.

    -   A subdomain name has the same creation restrictions as a Second-Level Domain.
    -   You can use multiple subdomains split with periods to create longer names.
    -   There is no limit to the number of subdomains you can create for your domain name.

Example: admin.platform.google.com

    - “admin” & “platform” | These two are both subdomains
    - “google” | This would be the Second-Level domain
    - “com” | This would be the Lop-Level domain (TLD)

#### Record Types

-   A records resolve to IPv4 addresses, for example, 104.26.10.229.

-   AAAA records resolve to IPv6 addresses, for example, 2606:4700:20:15:681a:be5.

-   CNAME records resolve to another domain name, for example, tryhackme’s online shop has the subdomain name store.tryhackme.com which returns a CNAME record shops.shopify.com. Another DNS request would then be made to shops.shopify.com to work out the IP address.

-   MX records resolve to the address of the servers that handle the email for the domain you are querying, for example, an MX record response for tryhackme.com would look something like alt1.aspmx.l.google.com. These records also come with a priority flag. This tells the client in which order to try the servers, this is perfect for if the main server goes down and email needs to be sent to a backup server.

-   TXT records are free text fields where any text-based data can be stored. TXT records have multiple uses, but some common ones can be to list servers that have the authority to send an email on behalf of the domain (this can help in the battle against spam and spoofed email). They can also be used to verify ownership of the domain name when signing up for third-party services.

#### Making a request

-   The Steps for a DNS Request

    -   When you request a domain name, your computer first checks its local cache to see if you’ve previously looked up the address recently; if not, a request to your Recursive DNS Server will be made.
    
    -   A Recursive DNS Server is usually provided by your ISP, but you can also choose your own. This server also has a local cache of recently looked-up domain names. If a result is found locally, this is sent back to your computer, and your request ends here (this is common for popular and heavily requested services such as Google, Facebook, and Twitter). If the request cannot be found locally, a journey begins to find the correct answer, starting with the internet’s root DNS servers.
    
    -   The root servers act as the DNS backbone of the internet; their job is to redirect you to the correct Top Level Domain Server, depending on your request. If, for example, you request www.cybersecurity.com, the root server will recognize the Top Level Domain of .com and refer you to the correct TLD server that deals with .com addresses.
    
    -   The TLD server holds records for where to find the authoritative server to answer the DNS request. The authoritative server is often also known as the nameserver for the domain. For example, the name server for tryhackme.com is kip.ns.cloudflare.com and uma.ns.cloudflare.com. You’ll often find multiple nameservers for a domain name to act as a backup in case one goes down.
    
    -   An authoritative DNS server is the server that is responsible for storing the DNS records for a particular domain name and where any updates to your domain name DNS records would be made. Depending on the record type, the DNS record is then sent back to the Recursive DNS Server, where a local copy will be cached for future requests and then relayed back to the original client that made the request. DNS records all come with a TTL (Time To Live) value. This value is a number represented in seconds that the response should be saved for locally until you have to look it up again. Caching saves on having to make a DNS request every time you communicate with a server.

    - ![DNS Request](Screenshot%202025-05-23%20194910.png)
