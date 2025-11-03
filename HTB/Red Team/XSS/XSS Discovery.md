
## [[Automated Discovery]]
Nessus, Burp Pro and ZAP are examples of [[Web Application Vulnerability Scanners]]. These scanners usually do two types of scanning: A Passive Scan which reviews client-side code for potential [[DOM-based XSS]] and an Active Scan, which sends various types of payloads to attempt to trigger an [[XSS]] through payload injection in the page source. 

Some of the common open-source tools that can assist us in XSS discovery are XSS Strike, Brute XSS, and XSSer.

## Manual discovery
When it comes to manual XSS discovery, the difficulty of finding the XSS vuln depends on the level of security of the web application. Basic XSS vulnerabilities can usually be found though testing various [[XSS Payloads]], but identifying advanced XSS vulnerabilities requires advanced code review skills.