Headers pass information between the client and the server.
Some headers are only used with either *requests* or *responses* and some other are for general use.

These are the header categories:
- General headers
	- Used for requests and responses.
	- Used to describe the message rather than its content.
- Entity headers
	- Used for requests and responses.
	- Used to describe the content.
- Request headers
	- Client sends these requests.
	- They DO NOT relate to the content.
	- For example, Host, User-Agent, Referer, Accept, Cookie, Authorization.
- Response headers
	- Are used to provide more context about the response.
	- For example, Server, Set-Cookie, WWW-Authenticate.
- Security headers
	- These are a class of *response headers* used to specify certain rules and policies.
	- For example, Content-Security-Policy, Strict-Transport-Security, Referrer-Policy.