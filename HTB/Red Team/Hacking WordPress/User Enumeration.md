
Enumerating a list of valid users is a critical phase of a WordPress security assessment. 

## First Method
It'd be reviewing posts to uncover the ID assigned to the user and their corresponding username. 

The admin user is usually assigned the user ID 1. 

This can also be done with curl:
```
curl -s -I http://[IP]/?author=1
```
We may get a 404 code if the user is not found.


## Second Method
This one requires interaction with the JSON endpoint, which allows us to obtain a list of users. This was changed in [[WP]] core after version **4.7.1**, and later versions only show whether a user is configured or not.

```
curl [URL]/wp-json/wp/v2/users | jq
```
