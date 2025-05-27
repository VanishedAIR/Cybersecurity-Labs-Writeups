## GET ([HTB](https://academy.hackthebox.com/module/35/section/247))

### Task Summary:

-   Find out what is wrong with the exercise using devtools to see the requests and use cURL to search for flag.
-   The way I did it was test with normal `curl 94.237.48.68:59874` but it said access denied meaning it requires some kind of authenticate.
-   To provide authentication i used `curl -u admin:admin 94.237.48.68:59874` because we were given the username and password.
-   A hint in the reading was to use the alternate version of authenticating which was shown by using `curl -v 94.237.48.68:59874` which said `Authorization: Basic YWRtaW46YWRtaW4`.
-   However we were told to enter the keyword flag, and in doing so I noticed the request in the website devtools saying it said `/search.php?search=flag`.
-   So I combined everything I learned and used `curl 'https://94.237.48.68:59874/search.php?search=flag' -H 'Authorization: Basic YWRtaW46YWRtaW4'` which revealed the flag to be `flag: HTB{curl_g3773r}`.

### Summary:

-   Whenever we visit any URL, our browsers default to a GET request to obtain the remote resources hosted at that URL.
-   Once the browser receives the initial page it is requesting; it may send other requests using various HTTP methods.
-   This can be observed through the Network tab in the browser devtools

### HTTP Basic Auth

-   When we visit the exercise found at the end of this section, it prompts us to enter a username and a password.
-   Unlike the usual login forms, which utilize HTTP parameters to validate the user credentials (e.g. POST request), this type of authentication utilizes a basic HTTP authentication, which is handled directly by the webserver to protect a specific page/directory, without directly interacting with the web application.

-   To access the page, we have to enter a valid pair of credentials, which are admin:admin in this case:

-   ![auth](https://academy.hackthebox.com/storage/modules/35/http_auth_login.jpg)

-   Once we enter the credentials, we would get access to the page:

-   ![auth-success](https://academy.hackthebox.com/storage/modules/35/http_auth_index.jpg)

-   ![curl-auth](Screenshot%202025-05-25%20214605.png)

-   As we can see, we get Access denied in the response body, and we also get Basic realm="Access denied" in the WWW-Authenticate header, which confirms that this page indeed uses basic HTTP auth, as discussed in the Headers section.
-   To provide the credentials through cURL, we can use the -u flag, as follows:

-   `curl -u admin:admin http://<SERVER_IP>:<PORT>/`

-   This time we do get the page in the response. There is another method we can provide the basic HTTP auth credentials, which is directly through the URL as (username:password@URL), as we discussed in the first section. If we try the same with cURL or our browser, we do get access to the page as well:

-   `curl http://admin:admin@<SERVER_IP>:<PORT>/`

### HTTP Authorization Header

-   If we add the -v flag to either of our earlier cURL commands:
-   ![-v](Screenshot%202025-05-25%20215616.png)

-   As we are using basic HTTP auth, we see that our HTTP request sets the Authorization header to Basic YWRtaW46YWRtaW4=, which is the base64 encoded value of admin:admin.
-   If we were using a modern method of authentication (e.g. JWT), the Authorization would be of type Bearer and would contain a longer encrypted token.
-   Let's try to manually set the Authorization, without supplying the credentials, to see if it does allow us access to the page.
-   We can set the header with the -H flag, and will use the same value from the above HTTP request. We can add the -H flag multiple times to specify multiple headers:

-   ![auth](Screenshot%202025-05-25%20220114.png)

-   As we see, this also gave us access to the page. These are a few methods we can use to authenticate to the page. Most modern web applications use login forms built with the back-end scripting language (e.g. PHP), which utilize HTTP POST requests to authenticate the users and then return a cookie to maintain their authentication.

### GET Parameters

-   Once we are authenticated, we get access to a City Search function, in which we can enter a search term and get a list of matching cities:

-   ![city-search](https://academy.hackthebox.com/storage/modules/35/http_auth_index.jpg)

-   As the page returns our results, it may be contacting a remote resource to obtain the information, and then display them on the page.
-   To verify this, we can open the browser devtools and go to the Network tab, or use the shortcut [CTRL+SHIFT+E] to get to the same tab.
-   Before we enter our search term and view the requests, we may need to click on the trash icon on the top left, to ensure we clear any previous requests and only monitor newer requests:

-   ![network](https://academy.hackthebox.com/storage/modules/35/network_clear_requests.jpg)

-   After that, we can enter any search term and hit enter, and we will immediately notice a new request being sent to the backend:

-   ![network](https://academy.hackthebox.com/storage/modules/35/web_requests_get_search.jpg)

-   When we click on the request, it gets sent to search.php with the GET parameter search=le used in the URL.
-   This helps us understand that the search function requests another page for the results.

-   Now, we can send the same request directly to search.php to get the full search results, though it will probably return them in a specific format (e.g. JSON) without having the HTML layout shown in the above screenshot.

-   To send a GET request with cURL, we can use the exact same URL seen in the above screenshots since GET requests place their parameters in the URL.
-   However, browser devtools provide a more convenient method of obtaining the cURL command.
-   We can right-click on the request and select Copy>Copy as cURL.
-   Then, we can paste the copied command in our terminal and execute it, and we should get the exact same response:
-   `curl 'http://<SERVER_IP>:<PORT>/search.php?search=le' -H 'Authorization: Basic YWRtaW46YWRtaW4='`

-   We can also repeat the exact request right within the browser devtools, by selecting Copy>Copy as Fetch. This will copy the same HTTP request using the JavaScript Fetch library. Then, we can go to the JavaScript console tab by clicking [CTRL+SHIFT+K], paste our Fetch command and hit enter to send the request:

-   ![js-console](https://academy.hackthebox.com/storage/modules/35/web_requests_fetch_search.jpg)
