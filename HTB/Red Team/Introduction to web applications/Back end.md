
The back end of a web app drives all of the core functionalities. This is the part we may never see or directly interact with.

There are four main back end components for web apps:

- Back end servers
	- Linux, Windows or Containers (Docker).
- Web servers
	- Apache, NGINX, IIS
- Databases
	- MySQL, MSSQL, Oracle, PostgreSQL.
	- Non relational databases: NoSQL  MongoDB.
- Development Frameworks:
	- Laravel (PHP)
	- ASP .NET (C#)
	- Spring (Java)
	- Django (Python)
- ![[Screenshot_2024-05-11_14-30-55.png]]

**Top 20 most common mistakes:**
- Permitting invalid data to enter the database
- Focusing on the system as a whole
- Establishing personally developed security methods
- Treating security to be your last step
- Developing plain text password storage
- Creating weak passwords
- Storing unencrypted data in the db
- Depending excessively on the client side
- Being too optimistic
- Permitting variables via the url path name
- Trusting third-party code
- Hard-coding backdoor accounts
- Unverified SQL injections
- Remote file inclusions
- Insecure data handling
- Failing to encrypt data properly
- Not using a secure cryptographic system
- Ignoring layer 8
- Review user actions
- Web app firewall misconfigs

[[OWASP]] Top 10 vulns
- Broken access control
- Cryptographic failures
- Injection
- Insecure design
- Security misconfigs
- Vulnerable and outdated components
- Identification and authentication failures
- Security logging and monitoring failures
- SSRF