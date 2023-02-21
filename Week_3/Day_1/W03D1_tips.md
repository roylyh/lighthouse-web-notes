# Roy's note

## Tips
- Web Server: Node.js
- Middleware: Express
- Template Engine: EJS

## Projects
[All Projects need to do](https://web.compass.lighthouselabs.ca/projects)s

## List of HTTP status codes
[List of HTTP status codes](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error)

# Template Engine
EJS [How To Use EJS to Template Your Node Application](https://www.digitalocean.com/community/tutorials/how-to-use-ejs-to-template-your-node-application)  
*Create a new file called _header.ejs inside the new partials directory.Notice that the name of this file starts with an underscore (_). This is to signify that it's a partial, in this case, a header partial.*  
The syntax for includes has changed in the latest version of EJS. Use:
```
<%- include('partials/_header') %>
```

## CRUD
Almost all web applications allow users to manipulate data in various ways, which we typically break down into four categories: *Create, Read, Update and Delete*.
| Action      | Description | HTTP Method | 
| ----------- | ----------- | ----------- |
| Create      | Add a new record       | GET |
| Read        | Retrieve the value of a record        | POST |
| Update      | Update a record's value        | PUT |
| Delete      | 	Delete a record        | DELETE |

## tips
curl -i <url> show the response with header  
[curl documentation](https://curl.se/docs/manpage.html)
The order of route definitions matters! The GET /urls/new route needs to be defined before the GET /urls/:id route. Routes defined earlier will take precedence, so if we place this route after the /urls/:id definition, any calls to /urls/new will be handled by app.get("/urls/:id", ...) because Express will think that new is a route parameter. **A good rule of thumb to follow is that routes should be ordered from most specific to least specific.**


```javascript
// generate Ramdom String
const generateRandomString = function(length = 6) {
  return Math.random().toString(20).substring(2,length + 2);
};
```