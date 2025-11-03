HTTP means Hyper Text Transfer Protocol

URL
- Resources over HTTP area accessed via a URL.
- ![[Screenshot_2024-05-05_14-14-43.png]]



| **Component** | **Example**       | **Description**                                                                                                                                       |
| ------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| Scheme        | http://           | Used to identify the protocol.                                                                                                                        |
| User info     | admin:password@   | Optional component that contains credentials used to authenticate the host                                                                            |
| Host          | inlanefreight.com | This signifies the resource location. Can be the host name or an IP.                                                                                  |
| Port          | :80               | If not specified, it defaults to 80 or 443 for https                                                                                                  |
| Path          | /dashboard.php    | Points to resource. Can be a file or folder. Otherwise it defaults to index.html                                                                      |
| Query string  | ?Login=true       | It starts with ? and consists of a parameter (login) and a value (true). Multiple parameters can be separated by &.                                   |
| Fragments     | #status           | Fragments are processed by the browsers on the client-side to locate sections within the primary resource (e.g. a header or section on the page).<br> |
![[Screenshot_2024-05-05_14-37-59.png]]

[[curl]]

- from client URL, is a command that primarily supports HTTP and other protocols.
- We can send a basic http request to any URL by using it as an argument for curl:
```
	 curl inlanefreight.com

```

- When we use curl, the html/js/css code does not render like a browser, but we see a rather raw format.
- We can also download a page or a file and output the content into a file using the -0 flag. If we want to specify the file name we can use -o