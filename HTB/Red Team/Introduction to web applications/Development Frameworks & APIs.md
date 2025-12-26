[[Frameworks]] help in developing core web app files and functionality. They make the implementation of functionalities easy and quick.
Common frameworks:
- Laravel (PHP)
- Express (Node.js)
- Django (Python)
- Rails (Ruby)

[[API]]
Application Programming Interface.
For the front end to interact with the back end and ask for certain tasks to be carried out, APIs are utilized.

**Query parameters**
The default method of sending specific arguments to a web page is through GET and POST request parameters.
Query parameters allow a single page to receive various types of input, each of which can be processed differently.

**Web APIs**
It is what allows remote access to functionality on the back end components.
To enable the use of APIs within a web application, the devs have to program this functionality on the back end by using API standards like SOAP or REST.

[[SOAP]]
Simple Objects Access.
This standard shares data though XML, where the request is made in XML though an HTTP request and the response is also returned in XML.

Example:
```xml
<?xml version="1.0"?>

<soap:Envelope
xmlns:soap="http://www.example.com/soap/soap/"
soap:encodingStyle="http://www.w3.org/soap/soap-encoding">

<soap:Header>
</soap:Header>

<soap:Body>
  <soap:Fault>
  </soap:Fault>
</soap:Body>

</soap:Envelope>
```
**SOAP** is very useful for transferring structured data or even binary data and is often used with serialized objects.
However, **SOAP** may be difficult to use for beginners or require long and complicated requests even for smaller queries.

[[REST]]
Representational State Transfer.
This standard shares data through the URL path and usually returns the output in JSON format.
REST APIs usually focus on pages that expect one type of input passed directly through the URL path, without specifying its name or type.

Example:
```json
{

  "100001": {
    "date": "01-01-2021",
    "content": "Welcome to this web application."
  },
  "100002": {
    "date": "02-01-2021",
    "content": "This is the first post on this web app."
  },
  "100003": {
    "date": "02-01-2021",
    "content": "Reminder: Tomorrow is the ..."
  }
}
```

**REST** uses various HTTP methods to perform different actions:
- GET to retrieve data
- POST to create data
- PUT to create or replace existing data
- DELETE to remove data