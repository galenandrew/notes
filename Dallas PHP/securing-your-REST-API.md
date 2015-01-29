# Securing Your REST API
@speaker Chris Cornutt, @enygma
@url websec.io
@date 2013-11-12

## Announcements
### Bright March, LLC
- Vic…
- LoneStarDev.org
- Taught at UT Dallas

## APIs
- You're thinking about two things
	- Incoming Requests
	- Outgoing Data

### Security Concepts
- …should be planned
- …is easy to ignore
- …is compromise (if it's difficult for users to use, they won't)

### Three Pillars
- Availability
- Scalability
- Reliability

## Authorization

### Authorization vs Authentication
- Authentication is when a user first accesses your website/app/api and says "this is who I am" and you try to validate the accuracy of 
- Authorization is when a user requests access to a resource and you determine yes/no

### Basic Auth
- Absolutely plain text
- base64_encoded string
- easily detected and decoded over HTTP

### Digest
- leverages md5 hashes
- uses nonce and opaque values

### Shared Tokens
- provider of the API creates tokens, then shares with the user
- trouble to maintain
- tokens are static, not asymmetric (e.g. it's using the same token over and over)
- tokens are not encryption

### OAuth v2
- "back and forth" between requestor and requested
- Burden of Identity is on the requestor
- Complex to implement
- OAuth v2 is for **authorization**, not _authentication_ (e.g. "this service can do _this_ with my information")
- Delegation

### Shared Certificates
- stronger protection than passwords
- no private information involved
- difficult to deploy


## Not Just Auth
### Rate Limiting
- if you're not rate limiting the requests to your API, you're not protecting it
- Examples of rate limiting:
	- requests/second, request/hour, etc
	- types of requests (lower response for GETs and higher response for POSTs, etc)
### Throttling
- Limit the amount of data
- slowing them down
- all about bandwidth…
- apache mods (cban)

### Filtering/Escaping
- JSON injection
- FILTER_VAR in PHP allows your to filer out many data types
- Data Type examples:
	- email
	- HTML
	- numeric
	- patterns/regex
	- boolean
	- IP
	- UTF-8
	- more…

### Direct Object Reference (DOR)

Yours: `GET /user/1/link/42`
Good Guesses:
- `GET /user/1/link/52`
- `PUT /user/1/link/42`

Alternatives:
- `GET /user/[GUID #1]/link/[GUID #2]`
- `GET /user/[username]`

### Error Conditions
- implement custom exceptions and error handling
- if you're not using proper error catching, the errors could display file paths, variable names, etc…opens up a whole other can of worms
- When sending an error in the response, make sure to change the HTTP response code to something other than 200!

### Use HTTPS
- by definition, an HTTPS server can not receive an unencrypted request
- **Enable HSTS headers**

### Stop Leaking
- e.g., error messages that output server information, file paths, etc

### Be stateless
- you shouldn't store the auth info between requests

### Authorize on resource, not URI
- e.g. you need to ensure auth access is granted to linked/nested information rather than just the URI being accesses

### Importance of HTTP status
- RFC 6585

### Use keys, not passwords
- **bcrypt** hashes the password uniquely every time, but will always validate (only available in PHP 5.5)

### Signing with hashes
- public/private hashes
- included in the headers

**THINK SIMPLE!**
