- Whenever web applications need to transfer files or move the user parameters from the URL they utilize [[POST]] requests.
- POST places user parameters *withing the HTTP request body*. Which has 3 benefits:
	- Lack of logging.
	- Less encoding requirements.
	- More data can be sent.

The -X POST flag sends  a POST request.

```
curl -X POST -d 'username=admin&password=admin' http://<SERVER_IP>:<PORT>/
```
**Since most websites redirect to another page upon log in, we can use the flag -L to follow redirects.**
If we see a search function code, we have succeeded. 

[[Authenticated cookies]]
- If we successfully authenticate, we receive a cookie, so we can use flags -v or -i to view the response, which should contain the Set-Cookie header with our authenticated cookie.

From devtools, we can go to storage and see our cookies there.

Example of curl with json search
```
curl -X POST -d '{"search":"flag"}' -b 'PHPSESSID=2siah5vqhvnidda62knf5cp5v3' -H 'Content-Type: application/json' http://<IP>/search.php
```
