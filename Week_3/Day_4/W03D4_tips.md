# Roy's notes

## Storing Passwords
**Hashing**:
* The original string is passed into a function that performs some kind of transformation on it and returns a different string (the _hash_)
* This is a one way process: a hashed value cannot be retrieved
**bcrypt**
```javascript
npm install bcryptjs
const bcrypt = require("bcryptjs");
const password = "purple-monkey-dinosaur"; // found in the req.body object
const hashedPassword = bcrypt.hashSync(password, 10);
bcrypt.compareSync("purple-monkey-dinosaur", hashedPassword); // returns true
bcrypt.compareSync("pink-donkey-minotaur", hashedPassword); // returns false

```


## Encrypted Cookies
Using "session-cookie"

### When to use...
* Plain Text Cookies:
  * Almost never use plain cookies
  * Maybe for:
    * Language selection
    * Shopping cart for non-logged in users
    * Analytics
* Encrypted Cookies:
  * Do this by default
  * Only store a way to uniquely identify the user (eg. `user_id` or `username` can be used to look up values in a database or object)

## HTTP Methods
- `PUT`: used to replace an existing resource
- `PATCH`: update part of an exisiting resource
- `DELETE`: delete an existing resource
  | **Method** | **Path** | **Purpose** |
  |:---:|:---|:---|
  | GET | /resources | Retrieve all of a resource (Browse) |
  | GET | /resources/:id | Retrieve a particular resource (Read) |
  | PUT | /resources/:id | Replace a resource (Edit) |
  | PATCH | /resources/:id | Update a resource (Edit) |
  | POST | /resources | Create a new resource (Add) |
  | DELETE | /resources/:id | Delete an existing resource (Delete) |

## Modular Routing
- Store routes in multiple files to keep them organized
- In Express, we need to use the Express.Router() method to give us back a **router** object
- All routes will be added to this _router_ object
- Finally, we export the _router_ object from the file to be imported into our Express server file (eg. `server.js`)

  ```js
  // post-router.js
  const express = require('express');
  const router = express.Router();

  router.get('/', (req, res) => {
    // typical route handler in here
    res.send('hello world');
  });

  module.exports = router;

  // server.js
  const postRouter = require('./routes/post-router');
  app.use('/posts', postRouter);
  ```

## Session Cookies vs. JSON Web tokens
“Http” is a “stateless” protocol, in that every http call made to a server is like a fresh call, with no memory or “state” of the previous calls.  
There are primarily two different approaches to session management,
- Session or Cookies based approach (server generates a cookie)
- JWT (JSON Web Tokens) based approach (server generates an access Token)

[npm jsonwebtoken](https://www.npmjs.com/package/jsonwebtoken)  
jwt.sign  
jwt.verify  
https://github.com/roylyh/JWT-Auth

