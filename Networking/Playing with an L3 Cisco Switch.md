
# Feb/1/206
So, let's play a little bit with this Cisco switch L3 functionality and CLI.
Before enabling the L3 functionality, let's make sure our stakeholders' (my girlfriend) production environment (her desktop computer) is on a separate network to avoid downtime.
![[IMG_2899.jpeg]]

So, now her computer is connected to that tp-link dumb switch which is connected directly to the router.

Lets see how my VLANs were set up.
![[Pasted image 20260201110644.png]]

My users:
![[Pasted image 20260201110724.png]]
> I had to do some special configs on my .ssh/config so I can ssh into the switch. 
![[Pasted image 20260201110859.png]]

Now, once I enable the L3 functionality, in theory, the switch will go back to its default config.
![[Pasted image 20260201111125.png]]
![[Pasted image 20260201111139.png]]
And...
Interesting. I still see the website, but that's because it's cached. The switch is currently rebooting.
![[Pasted image 20260201111229.png]]

We're back online!
![[Pasted image 20260201111436.png]]
We introduce the default password (username: cisco; password: cisco)
And we're prompted to create a new password:
![[Pasted image 20260201111528.png]]
Now, we see this:
![[Pasted image 20260201111557.png]]
Since I would like to learn the CLI more, I will try to enable SSH right away so we can go straight to it.

I'll try to do this from memory...
Let's go ahead and enable these 2:
![[Pasted image 20260201112041.png]]
And let's try to log in with password to see if that is enough...
![[Pasted image 20260201112153.png]]
Gotta save the config first...
![[Pasted image 20260201112231.png]]
Still no luck. Which means SSH must be enabled somewhere else as well.

Found it!
![[Pasted image 20260201112401.png]]

And since the public key of the switch changed after going to L3 mode, when trying to connect I'm greeted by this super friendly screen:
![[Pasted image 20260201112518.png]]
So since I'm 99.99% sure I'm not being hacked by a MITM attack, let's go ahead and delete the old key from the known_hosts file.

And there we go!
![[Pasted image 20260201112843.png]]
![[Pasted image 20260201112905.png]]

Now, let's set up the following:
- Hostname
- Another user
- Time
- VLANs
- Fun L3 stuff...

The easy way to find out how to do it, would be by asking your LLM of choice. Let's do it the old fashioned way. Books!
Jk jk, let's just Google it and let's aim for Cisco's documentation. It feels weird to call Googling old fashioned...

## hostname
So for hostname, we have this:
![[Pasted image 20260201113503.png]]

Let's give it a try:
![[Pasted image 20260201113553.png]]
Right off the bat, I messed it up. I was not in conf t mode (configure terminal).

## Add user
For this, I found a more thorough guide by Cisco.
```
https://www.cisco.com/c/en/us/td/docs/routers/asr9000/software/25xx/system-setup/configuration/guide/b-system-setup-cg-asr9000-25xx/create-user-profiles-and-assign-privileges.pdf
```
Let's read.

Cool workflow chart:
![[Pasted image 20260201114150.png]]
Very similar to what we'd do in Linux. Since my network is tiny and I will be the only person messing with it, I think creating a couple accounts with different privileges will suffice. One with low privileges to see what is considered sensitive and requires a higher level of access, and another one so I can actually do admin stuff.

> Turns out this guide is tailored for Cisco IOS XR, which appears to be an IOS version for high end routers. Gotta check what IOS version my switch comes with.

I don't see much with `show version` and I couldn't find an answer on which IOS version this Switch came with, so let's dig a bit more later.
![[Pasted image 20260201115231.png]]

Anyways...
Let's create a group:
![[Pasted image 20260201115533.png]]
OK, maybe we cannot create groups via CLI. (Since this is a Small Business switch, I wonder if the web UI has more functionalities than the CLI...)

Let's create a user then...
![[Pasted image 20260201120211.png]]

And there we have it `username <name> privilege <#> password <string>`.
![[Pasted image 20260201120343.png]]
I then created 2 more users. One with privilege of 7 and one with privilege of 1.

Now, as far as I know, this way of creating passwords is not secure since it is stored in plain text. So, we would have to use secret, instead of password.
For now, I'll leave it like that.

## Time
So, this time I found a Small Business-specific entry. Maybe there's a difference between Cisco CLI and Cisco IOS?
```
https://www.cisco.com/c/en/us/support/docs/smb/switches/cisco-small-business-300-series-managed-switches/smb5584-configure-system-time-settings-on-a-switch-through-the-comma.html
```

![[Pasted image 20260201121051.png]]
We're a tiny bit off...

As for our options, we have manual and automatic.
![[Pasted image 20260201121301.png]]
So, SNTP stands for Simple Network Time Protocol. I guess I could set that up on my Unifi Express?
But for now, let's manually set it up.

Let's enter config mode and then go for browser.
![[Pasted image 20260201121753.png]]
We now have to log in via browser.

![[Pasted image 20260201122039.png]]
It seems we're still a bit off. It's currently 12pm...
I went ahead and clicked the Import from your computer button and now it's OK. Unsure what might've gone wrong.


## VLANs
Now, let's set up VLANs!

These were my previous VLANs. Let's try to replicate them.
![[Pasted image 20260201110644.png]]

Testing the `vlan` command.
![[Pasted image 20260201125328.png]]
It seems I cannot name the VLANs from the CLI. So let's just create them and then we can rename them on the web UI.

Seems very intuitive. I messed up that last command though.
![[Pasted image 20260201125755.png]]
![[Pasted image 20260201125803.png]]

You can either set up the interfaces manually (1st pic) or using `range`. Pretty cool!
![[Pasted image 20260201130625.png]]
![[Pasted image 20260201131042.png]]

I then named the VLANs via web UI, and this is how it turned out:
![[Pasted image 20260201132615.png]]
(I also made all ports but 7-10 access ports)
![[Pasted image 20260201132733.png]]

And these are my VLANs on my router:
![[Pasted image 20260201132917.png]]

----
TO DO next:
- Isolate Proxmox lab.
- Play with ACLs.
- Test L3 capabilities of the Switch.