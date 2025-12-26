
The damage and the scope of an [[XSS]] attack depends on the type of XSS, a [[Stored XSS]] being the most critical, while [[DOM XSS]] being less so.

One of the most common attacks usually used with store XSS vulnerabilities is [[Website Defacing Attacks]]. Defacing a website means changing its look for anyone who visits the website.

## Defacement Elements
We can utilize injected JavaScript code through XSS to make a web page look any way we like.

Three HTML elements are usually utilized to change the main look of a web page:
- Background color `document.body.style.background`
- Background `document.body.background`
- Page title `document.title`
- Page text `DOM.innerHTML`

We can utilize two or three of these elements to write a basic message to the web page and even remove the vulnerable element, such that it would be more difficult to quickly reset the web page.

## Changing background
To change a web page's background, we can choose a certain color or use an image. 

```html
<script>document.body.style.background = "##141d2b"</script>
```
