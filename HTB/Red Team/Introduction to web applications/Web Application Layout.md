
These layouts consist of many different layers that can be summarized with the following three main categories.

- Web Application Infrastructure:
	- Database needed for the web application to function.
- Web Application Components:
	- UI/UX, client and server
- Web Application Architecture:
	- All the relationships between the various web application components.

[[Web Application Infrastructure]]
Many different setups can be used. Also called *models*. The most common ones can be grouped like this:

- Client-Server
	- ![[Screenshot_2024-05-11_14-00-06.png]]
- One Server
	- ![[Screenshot_2024-05-11_14-00-50.png]]
- Many Servers - One Database
	- ![[Screenshot_2024-05-11_14-01-19.png]]
- Many Servers - Many Databases
	- ![[Screenshot_2024-05-11_14-01-40.png]]

[[Web Application Components]]
Can be broken into:
- Client
- Server
	- Webserver
	- Web Application Logic
	- Database
- Services (microservices)
	- 3rd Party Integrations
	- Web Application Integrations
- Functions (Serverless)

[[Web Application Architecture]]

The components of a web application are divided into three different layers, AKA Three Tier Architecture.

- Presentation Layer
	- UI process components that enable communication with the application and the system.
	- Can be access by the client via the web browser and are returned in the form of HTML, JS and CSS.
- Application Layer
	- Ensure that all client requests are correctly processed.
	- It checks authorization, privileges and the data passed onto the client.
- Data Layer
	- Works together with the application layer to determine exactly where the required data is stored and how can it be accessed.
- Example of web app architecture:
	- ![[Screenshot_2024-05-11_14-10-31.png]]
