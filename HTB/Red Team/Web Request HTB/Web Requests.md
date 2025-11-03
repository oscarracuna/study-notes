
[[Get]]
- Whenever we visit any URL, our browsers default to a GET request to obtain the remote resources hosted at that URL. Once the browser receives the initial page it is requesting; it may send other requests using various HTTP methods.
[[HTTP Basic Auth]]
- This requests is handled directly by the webserver to protect a specific page/directory without directly interacting with the web application.
- To use [[curl]] with authentication you can use the flag -u (-i let's you see the response headers) and the credentials:
```
	curl -u admin:admin http://<server_IP>:<PORT>/
	OR
	curl http://admin:admin@<server_IP>:<PORT>
```
![[Screenshot_2024-05-08_19-46-27.png]]

