
Steps to check:
- Ensure you're targeting a [[Wordpress]] site.
- Ensure you have access to the `xmlrpc.php` file. In general, it's found at ``https://URL/xmlrpc.php``
- It will be pointless to target an XML-RPC server which is disabled/hardcoded/tampered/not working.

```
curl -d '<?xml version="1.0" encoding="utf-8"?> 
<methodCall> 
<methodName>system.listMethods</methodName> 
<params></params> 
</methodCall>' http://[URL]/xmlrpc.php
```

## Brute force attacks

Sometimes the only way to bypass request limiting or blocking in a brute force attack against [[WP]] site is to use the all too forgotten XML-RPC API.
