
It's important to know what type of app we are working with. Make sure you know the version number. This is helpful for common misconfigurations such as default passwords or searching for known vulnerabilities for a particular version. We can achieve this by reviewing the page source code:
```html
...SNIP...
<link rel='https://api.w.org/' href='http://blog.inlanefreight.com/index.php/wp-json/' />
<link rel="EditURI" type="application/rsd+xml" title="RSD" href="http://blog.inlanefreight.com/xmlrpc.php?rsd" />
<link rel="wlwmanifest" type="application/wlwmanifest+xml" href="http://blog.inlanefreight.com/wp-includes/wlwmanifest.xml" /> 
<meta name="generator" content="WordPress 5.3.3" />
...SNIP...
```
Or with this one-liner:
```shell
curl -s -X GET http://[url] | grep '<meta name="generator"'
```
Aside from version information, the source code may also contain comments that may be useful, like links to CSS or [[JS]].

In older [[Wordpress]] versions, another source of uncovering version information is the `readme.html` file in the [[WP]] root directory.