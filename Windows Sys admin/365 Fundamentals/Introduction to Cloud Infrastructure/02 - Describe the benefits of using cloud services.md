This title feels like a sales pitch.
Skipping the introduction and learning objectives. Ain't nobody got time for that.

---
# Describe the benefits of high availability and scalability in the cloud
"When building or deploying a cloud app, two of the biggest considerations are uptime (availability) and the ability to handle demand (scale)".

### High availability
In systems administration, uptime is king.

When using a Cloud Provider, an agreement on uptime (SLA - Service Level Agreement) must be set. They basically guarantee the app or service you're hosting on their servers will be up for an X amount of time (let's say 99.80% of the time) otherwise, depending on the agreement, they could be responsible for remunerating the losses you theoretically had during that downtime.

### Scalability
"Scalability refers to the ability to adjust resources to meet demand".

Now, I think this is the coolest thing about Cloud.
Imagine you're a startup and you want to deploy your web app. Since you're barely starting, you don't really know if your company is going to be like 90% of startups and inevitably fail, or if you're going to be the next Facebook, so it's hard to buy IT infra based on uncertainty, so you opt for a Cloud approach, which means you rent computing on a *consumption-based model*, so if you do indeed become the next Facebook, you will pay Facebook-level bills to Azure, but if you do not make it, your bill won't make it so you can't pay your employees.

I'm done with weird scenarios, so moving on...

Scalability can be defined in two kinds:

### Vertical scaling
Beefing up a server. Imagine it as stacking more stuff on one rack.

### Horizontal scaling
Buying more servers. Instead of stacking more stuff on one rack, you buy another rack.

These two concepts are not on-prem-exclusive. They also apply to cloud (just replace server with container/VM so it applies to cloud).

---

# Describe the benefits of reliability and predictability in the cloud

### Reliability
"Reliability is the ability of a system to recover from failures and continue to function".
Since the cloud is de-centralized, it's resilient by nature. If something happens on one datacenter, you can set up failovers so that your uptime is untouched.

### Predictability
Unsure about this one. Basically you should be able to predict how much and how well your rented server will perform?

"Predictability in the cloud lets you move forward with confidence. Predictability can be focused on performance predictability or cost predictability. Both performance and cost predictability are heavily influenced by the Microsoft Azure Well-Architected Framework. Deploy a solution built around this framework and you have a solution whose cost and performance are predictable."

---
# Describe the benefits of security and governance in the cloud

First off, what is governance and compliance? -> Basically, you (as a company) have to abide to certain standards and government regulatory requirements (if you don't comply, you may get shutdown or receive hefty bills from the govt).

Basically, in the cloud you can set up measures to make sure your systems are secure by either setting up automatic updates or designing templates that harden all of your servers.

---
# Describe the benefits of manageability in the cloud
I'll just copy and paste this one. Self explanatory.
### Management of the cloud**

Management of the cloud speaks to managing your cloud resources. In the cloud, you can:

- Automatically scale resource deployment based on need.
- Deploy resources based on a preconfigured template, removing the need for manual configuration.
- Monitor the health of resources and automatically replace failing resources.
- Receive automatic alerts based on configured metrics, so you’re aware of performance in real time.

### Management in the cloud

Management in the cloud speaks to how you’re able to manage your cloud environment and resources. You can manage these:

- Through a web portal.
- Using a command line interface.
- Using APIs.
- Using PowerShell.