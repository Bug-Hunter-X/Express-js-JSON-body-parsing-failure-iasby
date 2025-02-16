# Express.js JSON Body Parsing Failure

This repository demonstrates a common error in Express.js applications where the request body is not parsed correctly when using middleware that does not handle JSON requests. The issue arises when the middleware is placed before `express.json()`, resulting in an empty request body.

## Bug Description

The provided Express.js application attempts to parse JSON data sent in a POST request to the `/data` route. However, it fails to parse the request body correctly, resulting in `req.body` being undefined or empty. This happens because a non-JSON middleware may be inadvertently placed before the `express.json()` middleware, preventing the latter from parsing the JSON data.