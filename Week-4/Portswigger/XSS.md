# Lab: Reflected XSS into HTML context with nothing encoded ([Port Swigger](https://portswigger.net/web-security/cross-site-scripting/reflected/lab-html-context-nothing-encoded))

## Task Summary:

- First time using port swiggers lab, and in this specific one, I was told to perform a cross-site scripting attack that calls the alert function.
- With the instructions giving the clue to the fact that I need to look for a input search field, I quickly realized I had to mess around with the search function of the website
- ![search](Screenshot%202025-06-15%20190413.png)
- For a test search I entered `<h3>Hello Test<h3>` and just like I expected and the instructions were hinting, the code logic allowed for html tags to be included.
- ![hello-test-image](Screenshot%202025-06-15%20190812.png)
- To finish the lab I inputted `<script>alert(1)</script>` like I was told by the instruction to finish the lab
- ![burp-script](Screenshot%202025-06-15%20192148.png)
- Another thing to notice is the fact that the search query also shows up in the url as parameters, meaning if we wanted to sent a target user a link, we could send a link with parameters which would execute on click. This detail was pointed out in a walkthrough video underneath the lab instructions that I happen to click on accidentally.
- ![search-param-scripts](Screenshot%202025-06-15%20192311.png)