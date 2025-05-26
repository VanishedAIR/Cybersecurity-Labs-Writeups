## POST ([HTB](https://academy.hackthebox.com/module/35/section/224))

### Task Summary:

-   Knowing the fact that this specific website requires a login and creates a POST request, we were told to retrieve a flag using cURL.
-   I first started with trying to login in with `curl -d 'username=admin&password=admin' 94.237.54.192:52199` which worked then I added a -v flag to see the set-cookie which came out to be `Set-Cookie: PHPSESSID=mab8esfte4vgoesc1qmkhtg9sf`.
-   I then used the -X tag to say im making a post request with the -b tag and inputting the set-cookie for authentication into 94.237.54.192:52199 which looked like `curl -X POST -b 'PHPSESSID=mab8esfte4vgoesc1qmkhtg9sf' 94.237.54.192:52199/search.php` and it gave me a clue, which was `Content type much be: application/json`.
-   From there I realized I should pass in the header using `-H Content-Type: application/json` but I was forgetting that we are searching for the flag which was the input in the search field, so we had to pass in the data using the -d tag.
-   The final command that revealed the flag come out to be `curl -X POST -d '{"search":"flag"}' -b 'PHPSESSID=mab8esfte4vgoesc1qmkhtg9sf' 94.237.54.192:52199/search.php -H 'Content-Type: application/json'`

### Summary

-   GET requests may be used by web applications for functionalities like search and accessing pages.
-   However, whenever web applications need to transfer files or move the user parameters from the URL, they utilize POST requests.
-   Unlike HTTP GET, which places user parameters within the URL, HTTP POST places user parameters within the HTTP Request body.

### Advantages of POST

-   POST requests provide several benefits:
    -   **Lack of Logging**: As POST requests may transfer large files (e.g. file upload), it would not be efficient for the server to log all uploaded files as part of the requested URL, as would be the case with a file uploaded through a GET request.
    -   **Less Encoding Requirements**: URLs are designed to be shared, which means they need to conform to characters that can be converted to letters. The POST request places data in the body which can accept binary data. The only characters that need to be encoded are those that are used to separate parameters.
    -   **More data can be sent**: The maximum URL Length varies between browsers (Chrome/Firefox/IE), web servers (IIS, Apache, nginx), Content Delivery Networks (Fastly, Cloudfront, Cloudflare), and even URL Shorteners (bit.ly, amzn.to). Generally speaking, a URL's lengths should be kept to below 2,000 characters, and so they cannot handle a lot of data.

### Login Forms

-   In the exercise, we see that it utilizes a PHP login form instead of HTTP basic auth:

![login-form](https://academy.hackthebox.com/storage/modules/35/web_requests_post_login.jpg)

-   If we try to login with admin:admin, we get in and see a similar search function to the one we saw earlier in the GET section:

![logged-in](https://academy.hackthebox.com/storage/modules/35/web_requests_login_search.jpg)

-   If we clear the Network tab in our browser devtools and try to log in again, we will see many requests being sent.
-   We can filter the requests by our server IP, so it would only show requests going to the web application's web server.
-   We'll notice a POST request being sent:

![network-tab](https://academy.hackthebox.com/storage/modules/35/web_requests_login_request.jpg)

-   We can click on the request, click on the Request tab, and then click on the Raw button to show the raw request data.
-   We see the following data being sent as the POST request data:
    -   `username=admin&password=admin`

### Using cURL for POST Requests

-   We will use the -X POST flag to send a POST request.
-   To add our POST data, we can use the -d flag and add the data after it:
    -   `curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/`
-   **Tip:** Many login forms would redirect us to a different page once authenticated (e.g. /dashboard.php). If we want to follow the redirection with cURL, we can use the -L flag.

### Authenticated Cookies

-   If we were successfully authenticated, we should have received a cookie so our browsers can persist our authentication.
-   We can use the -v or -i flags to view the response, which should contain the Set-Cookie header with our authenticated cookie:

![set-cookies](Screenshot%202025-05-26%20104126.png)

-   With our authenticated cookie, we should now be able to interact with the web application without needing to provide our credentials every time.
-   To test this, we can set the cookie with the -b flag in cURL:

    -   `curl -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://<SERVER_IP>:<PORT>/`

-   We can also specify the cookie as a header:
    -   `curl -H 'Cookie: PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' http://<SERVER_IP>:<PORT>/`

### Managing Cookies in Browser

-   We can also manage cookies directly in our browsers.
-   Let's first logout to get back to the login page.
-   Then, we can go to the Storage tab in the devtools with [SHIFT+F9].
-   In the Storage tab, we can click on Cookies in the left pane and select our website to view our current cookies.
-   If we were logged out, then our PHP cookie should not be authenticated, which is why we get the login form and not the search function:

![logged-out-storage](https://academy.hackthebox.com/storage/modules/35/web_requests_cookies.jpg)

-   Now, let's try to use our earlier authenticated cookie, and see if we do get in without needing to provide our credentials.
-   To do so, we can simply replace the cookie value with our own.
-   Otherwise, we can right-click on the cookie and select Delete All, and the click on the + icon to add a new cookie. - After that, we need to enter the cookie name, which is the part before the = (PHPSESSID), and then the cookie value, which is the part after the = (c1nsa6op7vtk7kdis7bcnbadf1).
-   Then, once our cookie is set, we can refresh the page, and we will see that we do indeed get authenticated without needing to login, simply by using an authenticated cookie:

![auth-with-cookies](https://academy.hackthebox.com/storage/modules/35/web_requests_auth_cookie.jpg)

### JSON Data

-   Finally, let's see what requests get sent when we interact with the City Search function. To do so, we will go to the Network tab in the browser devtools, and then click on the trash icon to clear all requests. Then, we can make any search query to see what requests get sent:

![requests](https://academy.hackthebox.com/storage/modules/35/web_requests_search_request.jpg)

-   As we can see, the search form sends a POST request to search.php, with the following data:

-   `{"search":"london"}`

-   The POST data appear to be in JSON format, so our request must have specified the Content-Type header to be application/json. We can confirm this by right-clicking on the request, and selecting Copy>Copy Request Headers:

-   ![copy-request-header](Screenshot%202025-05-26%20114444.png)

-   Indeed, we do have Content-Type: application/json. Let's try to replicate this request as we did earlier, but include both the cookie and content-type headers, and send our request to search.php:

-   `curl -X POST -d '{"search":"london"}' -b 'PHPSESSID=c1nsa6op7vtk7kdis7bcnbadf1' -H 'Content-Type: application/json' http://<SERVER_IP>:<PORT>/search.php`

-   We send the POST request with -X, the data with -d, the authentication cookie with -b, and header with -H and the link and get back `["London (UK)"]`

-   We were able to interact with the search function directly without needing to login or interact with the web application front-end. This can be an essential skill when performing web application assessments or bug bounty exercises, as it is much faster to test web applications this way.

-   Finally, let's try to repeat the same above request by using Fetch, as we did in the previous section. We can right-click on the request and select Copy>Copy as Fetch, and then go to the Console tab and execute our code there:

-   ![fetch](https://academy.hackthebox.com/storage/modules/35/web_requests_fetch_post.jpg)
