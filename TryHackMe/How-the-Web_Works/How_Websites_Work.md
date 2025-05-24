## How Websites Work ([TryHackMe - YouTube](https://www.youtube.com/watch?v=iWoiwFRLV4I&list=PL0iJrrpaWpyU5OQnrSis1Qjt_UYjkvCKd&index=3))

### Task Summary:

-   First simulation consisted of a simple rendering of HTML code to visualize how HTML code works
-   Second simulation consisted of a simple HTML+JavaScript visualization, on how we can use JavaScript for real-time changes to the website
-   Third simulation consisted of trying to see if any comments or login credentials were shown in the source code which were supposed to be hidden. Sure enough, checking the websites source code revealed that there was a comment that provided access to admin user on the website.
-   The Fourth simulation consisted of seeing if we were able to inject html using an input field, because if the input is not sanitized then we can inject html, which is what we did in this case.

### Summary:

#### How websites work

-   When you visit a website your browser (like Safari or Google Chrome) makes a request to a web server asking for information about the page you’re visiting and will respond with data that your browser uses to show you the page; a web server is just a dedicated computer somewhere else in the world that handles your requests.

![user2server](https://miro.medium.com/v2/resize:fit:720/format:webp/0*5rR6cuZe5bl4d0gn.png)

-   There are two major components that make up a website:

    -   Front End (Client-Side) — the way your browser renders a website.
    -   Back End (Server-Side) — a server that processes your request and returns a response.

-   You make a request to a server and it responds with data your browser uses to render information to you.

#### HTML

-   Websites are primarily created using:

    -   HTML, to build websites and define their structure
    -   CSS, to make websites look pretty by adding styling options
    -   JavaScript, implement complex features on pages using interactivity

-   HyperText Markup Language (HTML) is the language websites are written in.
-   Elements (also known as tags) are the building blocks of HTML pages and tells the browser how to display content.
-   The code snippet below shows a simple HTML document, the structure of which is the same for every website:

![html](https://miro.medium.com/v2/resize:fit:640/format:webp/0*dQuYza_Jcc5b0I0_.png)

-   The HTML structure (as shown in the screenshot) has the following components:

    -   The `<!DOCTYPE html>` defines that the page is a HTML5 document. This helps with standardization across different browsers and tells the browser to use HTML5 to interpret the page.
    -   The `<html>` element is the root element of the HTML page - all other elements come after this element.
    -   The `<head>` element contains information about the page (such as the page title)
    -   The `<body>` element defines the HTML document's body, only content inside of the body is shown in the browser.
    -   The `<h1>` element defines a large heading
    -   The `<p>` element defines a paragraph
    -   There are many other elements (tags) used for different purposes. For example, there are tags for: buttons (`<button>`), images (`<img>`), lists, and much more.

-   Tags can contain attributes such as the class attribute which can be used to style an element (e.g. make the tag a different color) `<p class="bold-text">`, or the src attribute which is used on images to specify the location of an image: `<img src="img/cat.jpg">`.
-   An element can have multiple attributes each with its own unique purpose e.g. `<p attribute1="value1" attribute2="value2">`

-   Elements can also have an id attribute (`<p id="example">`), which is unique to the element.
-   Unlike the class attribute where multiple elements can use the same class, an element must have different id's to uniquely identify them.
-   Element id's are used for styling and to identify it by JavaScript.

#### JavaScript

-   HTML is used to create the website structure and content, while JavaScript is used to control the functionality of webpages — without JavaScript a page would not have interactive elements, and would always be static.
-   JS can dynamically update the page in real-time, giving functionality to change the style of a button when a particular event on the page occurs (such as when a user clicks a button), or to display moving animations.

-   JavaScript is added within the page source code and can be either loaded within `<script>` tags or can be included remotely with the src attribute: `<script src="/location/of/javascript_file.js"></script>`

-   The following JavaScript code finds a HTML element on the page with the id of “demo” and changes the element’s contents to “Hack the Planet” : `document.getElementById("demo").innerHTML = "Hack the Planet";`

-   HTML elements can also have events, such as “onclick” or “onhover” that execute JavaScript when the event occurs.
-   The following code changes the text of the element with the demo ID to Button Clicked: `<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>` - onclick events can also be defined inside the JavaScript script tags, and not on elements directly.

#### Sensitive Data Exposure

-   Sensitive Data Exposure is when a website doesn’t properly protect (or remove) sensitive clear-text information to the end-user; usually found in the frontend source code of sites.

-   We now know that websites are built using many HTML elements (tags), all of which we can see by simply “viewing the page source”, a website developer may have forgotten to remove login credentials, hidden links to private parts of the website or other sensitive data shown in HTML or JavaScript.

![sensitive-source-code](https://miro.medium.com/v2/resize:fit:720/format:webp/0*eeOJIb_v8UCd0vcl.png)

-   Sensitive information can be potentially leveraged to further an attacker’s access within different parts of a web application.
-   For example, there could be HTML comments with temporary login credentials, and if you viewed the page’s source code and found this, you could use these credentials to login elsewhere on the application (or worse, used to access other backend components of the site).

-   Whenever you’re assessing a web application for security issues, one of the first things you should do is review the page source code to see if you can find any exposed login credentials or hidden links.

#### HTML Injection

-   HTML Injection is a vulnerability that occurs when unfiltered user input is displayed on the page.
-   If a website fails to sanitize user input (filter any “malicious” text that a user inputs into a website), and that input is used on the page, an attacker can inject HTML code into a vulnerable website.

-   Input sanitization is very important in keeping a website secure, as information a user inputs into a website is often used in other frontend and backend functionality.
-   Another vulnerability is database injection, where you can manipulate a database lookup query to login as another user by controlling the input that’s directly used in the query
-   When a user has control of how their input is displayed, they can submit HTML (or JavaScript) code and the browser will use it on the page, allowing the user to control the page’s appearance and functionality.
    ![injection](https://miro.medium.com/v2/resize:fit:720/format:webp/0*f0laehxyfJ_pc5Lw.png)

-   The image above shows how a form outputs text to the page.
-   Whatever the user inputs into the “What’s your name” field is passed to a JavaScript function and output to the page, which means if the user adds their own HTML or JavaScript in the field it’s used in the sayHi function and is added to the page — this means you can add your own HTML (such as a `<h1>` tag) and it will output your input as pure HTML.

-   The general rule is never to trust user input — to prevent malicious input the website developer should sanitize everything the user enters before using it in the JavaScript function; in this case, the developer could remove any HTML tags.
