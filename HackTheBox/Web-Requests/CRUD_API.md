## CRUD API ([HTB](https://academy.hackthebox.com/module/35/section/227))

### Task Summary:

- In this exercise I had to manipulate a city's name to flag by using `curl -X PUT http://94.237.60.52:30446/api.php/city/Boston -d '{"city_name":"flag"}' -H 'Content-Type: application/json'`
- Then I was told to remove a city and I chose London and did it by using `curl -X DELETE 94.237.60.52:30446/api.php/city/London`
- Then to retrieve the flag I was told to search for the city flag, and i did it by `curl 94.237.60.52:30446/api.php/city/flag` which revealed the flag to be `HTB{crud_4p!_m4n!pul4T0r}`

### Summary

### APIs

-   There are several types of APIs. Many APIs are used to interact with a database, such that we would be able to specify the requested table and the requested row within our API query, and then use an HTTP method to perform the operation needed.
-   For example, for the api.php endpoint in our example, if we wanted to update the city table in the database, and the row we will be updating has a city name of london, then the URL would look something like this:
-   `curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london ...SNIP...`

### CRUD

-   As we can see, we can easily specify the table and the row we want to perform an operation on through such APIs. Then we may utilize different HTTP methods to perform different operations on that row. In general, APIs perform 4 main operations on the requested database entity:

-   ![crud](Screenshot%202025-05-26%20143923.png)

-   These four operations are mainly linked to the commonly known CRUD APIs, but the same principle is also used in REST APIs and several other types of APIs. Of course, not all APIs work in the same way, and the user access control will limit what actions we can perform and what results we can see

### Read

-   The first thing we will do when interacting with an API is reading data. As mentioned earlier, we can simply specify the table name after the API (e.g. /city) and then specify our search term (e.g. /london), as follows:
-   `curl http://<SERVER_IP>:<PORT>/api.php/city/london` => `[{"city_name":"London","country_name":"(UK)"}]`

-   We see that the result is sent as a JSON string. To have it properly formatted in JSON format, we can pipe the output to the jq utility, which will format it properly. We will also silent any unneeded cURL output with -s, as follows:

-   ![jq](Screenshot%202025-05-26%20150345.png)

-   Finally, we can pass an empty string to retrieve all entries in the table:

-   `curl -s http://<SERVER_IP>:<PORT>/api.php/city/ | jq`

`[`
`  {`
`    "city_name": "London",`
`    "country_name": "(UK)"`
`  },`
`  {`
`    "city_name": "Birmingham",`
`    "country_name": "(UK)"`
`  }`,
`  {`
`    "city_name": "Leeds",`
`    "country_name": "(UK)"`
`  },`
`  ...SNIP...`
`]`


### Create

- To add a new entry, we can use an HTTP POST request, which is quite similar to what we have performed in the previous section. We can simply POST our JSON data, and it will be added to the table. As this API is using JSON data, we will also set the Content-Type header to JSON, as follows:

- `curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'`

- To check `curl -s http://<SERVER_IP>:<PORT>/api.php/city/HTB_City | jq`

`[`
  `{`
    `"city_name": "HTB_City",`
    `"country_name": "HTB"`
  `}`
`]`

### Update

- Now that we know how to read and write entries through APIs, let's start discussing two other HTTP methods we have not used so far: PUT and DELETE.
- PUT is used to update API entries and modify their details, while DELETE is used to remove a specific entity.

- **Note:** The HTTP PATCH method may also be used to update API entries instead of PUT. To be precise, PATCH is used to partially update an entry (only modify some of its data "e.g. only city_name"), while PUT is used to update the entire entry. We may also use the HTTP OPTIONS method to see which of the two is accepted by the server, and then use the appropriate method accordingly. In this section, we will be focusing on the PUT method, though their usage is quite similar.

- Using PUT is quite similar to POST in this case, with the only difference being that we have to specify the name of the entity we want to edit in the URL, otherwise the API will not know which entity to edit. So, all we have to do is specify the city name in the URL, change the request method to PUT, and provide the JSON data like we did with POST, as follows:

- `curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'`

- **Note:** In some APIs, the Update operation may be used to create new entries as well. Basically, we would send our data, and if it does not exist, it would create it. For example, in the above example, even if an entry with a london city did not exist, it would create a new entry with the details we passed.

### Delete

- Finally, let's try to delete a city, which is as easy as reading a city. We simply specify the city name for the API and use the HTTP DELETE method, and it would delete the entry, as follows:

- `curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City`

- To check if it deleted `curl -s http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City | jq` => `[]`
- After we deleted New_HTB_City, we get an empty array when we try reading it, meaning it no longer exists.

- With this, we are able to perform all 4 CRUD operations through cURL.
- In a real web application, such actions may not be allowed for all users, or it would be considered a vulnerability if anyone can modify or delete any entry.
- Each user would have certain privileges on what they can read or write, where write refers to adding, modifying, or deleting data.
- To authenticate our user to use the API, we would need to pass a cookie or an authorization header (e.g. JWT), as we did in an earlier section. Other than that, the operations are similar to what we practiced in this section.

