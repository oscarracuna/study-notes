[[API]]
- Advanced Programming Interface.
- Many APIs are used to interact with a database, such that we would be able to specify the requested row within our API query, and then use an HTTP method to perform the operation needed.

[[CRUD]]
- Create, Read, Update, Delete.
- POST, GET, PUT, DELETE.

**Read**
- The first thing we will do when interacting with an API is reading data.

When we curl a search, the data may be in JSON format, so we can pipe it to the jq utility also using the flag -s:
```shell
Rhaenesis@htb[/htb]$ curl -s http://<SERVER_IP>:<PORT>/api.php/city/london | jq

[
  {
    "city_name": "London",
    "country_name": "(UK)"
  }
]
```
**And we can pass an empty string to retrieve all entries in the table**

**Create**
- To add a new entry, we can use an HTTP POST request.
- If the API is using JSON data, we need to set the Content-Type to JSON.
```bash
Rhaenesis@htb[/htb]$ curl -X POST http://<SERVER_IP>:<PORT>/api.php/city/ -d '{"city_name":"HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```

**Update**
- [[PUT]] is used to update API entries.
	- We need to specific the entity we want to edit.
	```shell
Rhaenesis@htb[/htb]$ curl -X PUT http://<SERVER_IP>:<PORT>/api.php/city/london -d '{"city_name":"New_HTB_City", "country_name":"HTB"}' -H 'Content-Type: application/json'
```

- [[DELETE]] removes specific entity.
- [[PATCH]] can also be used to update.

**DELETE**
- We simply specify the entity that we want to delete.
```shell
Rhaenesis@htb[/htb]$ curl -X DELETE http://<SERVER_IP>:<PORT>/api.php/city/New_HTB_City
```
