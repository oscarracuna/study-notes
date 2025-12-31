
# Introduction to Microsoft Azure Fundamentals.
This is just an overview of what the course is, why you should take it, and the domain areas.

| **AZ-900 Domain Area**                   | **Weight** |
| ---------------------------------------- | ---------- |
| Describe cloud concepts                  | 25-30%     |
| Describe Azure architecture and services | 35-40%     |
| Describe Azure management and governance | 30-35%     |

----
# Introduction to cloud computing
More learning objectives zzzz

---
# What is cloud computing
Cloud computing is the delivery of computing services over the internet.
Entails IT infrastructure:
- Virtual Machines
- Storage
- Databases
- Networking

No need to own the IT infrastructure, which means easy scalability. If you need more power, just pay more. No need to buy a new server, just rent a more powerful one.

----
# Describe the shared responsibility model
Who is responsible for what?

In a corp data center, the company is responsible for maintaining the *physical*, ensuring security and replacing the servers if needed.The IT dept. is responsible for keeping *everything* up and running. From software to hardware.

Now, imagine that you have to be responsible for less stuff, such as maintaining and keeping the servers running. The shared responsibility model is just that; the *Cloud Provider* is responsible for the servers, you are responsible for *what* you store on those servers and making sure the info stored there is accessible for the right people/services.
![[Pasted image 20251227005552.png]]

# Define cloud models
There are three main models: 

### Private cloud
It's a cloud used by a single entity. Imagine your company got so big that it's now delivering IT services over the internet. It's just cloud without the shared responsibility since you own and are responsible for all the hardware.

### Public cloud
This one is built, controller and maintained by a third-party (cloud provider). Exactly what you think of when thinking of cloud. Hosting something on someone else's hardware.

### Hybrid cloud
Just a mix of both. Imagine you're hosting a web app on your own hardware, but instead of buying a new server for situations in which you will need more computing (Black Friday deals or something like that), you just rely on a Cloud Provider for those specific situations. Another example could be an AD/M365 hybrid environment.

**Some others:**
- Multi-cloud -> Using multiple Cloud Providers.Imagine hosting a web app on Azure and using Cloudflare as a WAF. (Networking does fall in the Cloud services umbrella.-> [[#What is cloud computing]])
- Azure Arc -> "Set of technologies that helps manage your cloud environment". Unsure about this one.
- Azure VMware Solution -> Imagine you're already hosting your VMs using VMware and want to migrate to cloud or do a hybrid approach.

----
# Describe the consumption-based model
There are two types of expenses in IT infra: *Capital expenditure* (CapEx) and *Operational expenditure* (OpEx).

### CapEx
Typically a one-time and up-front expenditure to purchase tangible resources.

### OpEx
Spending money on services or products over time.

> Basically, CapEx = buying a car in cash & OpEx = leasing a car.



