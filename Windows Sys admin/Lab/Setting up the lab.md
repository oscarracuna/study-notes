
## How to set up a Windows VM on Proxmox

1st, we are going to need an ISO. I will go for Windows IoT Enterprise. Why? Because it's not bloated. I won't go for Windows 10 because it's already EoL and I would like to future-proof this lab environment. 
Link:
```
https://www.microsoft.com/en-us/evalcenter/download-windows-11-iot-enterprise-ltsc-eval
```

Now, we are going to upload it to Proxmox

![[Pasted image 20251225205130.png]]
You can either upload the file (via file transfer) or Download from URL, which is what I ended up doing.

Once we have the ISO, we will also need to download the virtIO drivers so our internet works.

You can find the drivers here:
```
https://pve.proxmox.com/wiki/Windows_VirtIO_Drivers#Downloading_the_Wizard_in_the_VM
```

And then select either latest stable or most recent:

![[Pasted image 20251225214934.png]]
Copy the link and download the ISO to your Proxmox environment (or upload the file to Proxmox).

And now we can create the Windows VM:

![[Pasted image 20251225205618.png]]

![[Pasted image 20251225210605.png]]

![[Pasted image 20251225210736.png]]

![[Pasted image 20251225210815.png]]

![[Pasted image 20251225210826.png]]

![[Pasted image 20251225210837.png]]

![[Pasted image 20251225210906.png]]


Once the VM booted, I was greeted with this screen:
![[Pasted image 20251225211006.png]]
My first thought was "Woah, something might've gone wrong". But after a minute or so, it went away and I was able to see the Windows install screen:
![[Pasted image 20251225211159.png]]

![[Pasted image 20251225211213.png]]

![[Pasted image 20251225211402.png]]

Here's where the virtIO drivers are going to come handy.
Click Browse, go to the virtIO drive, amd64, win11 and press OK.
![[Pasted image 20251225211500.png]]

![[Pasted image 20251225211547.png]]

And here we can select the drive we want to install Windows on.
![[Pasted image 20251225211602.png]]

![[Pasted image 20251225211634.png]]

After a few minutes (much faster than I expected), we see this:
![[Pasted image 20251225212357.png]]

Since I don't want to create or link a Microsoft account, I selected "I don't have internet".
![[Pasted image 20251225212454.png]]

![[Pasted image 20251225212511.png]]

We make a super secure password.
![[Pasted image 20251225212541.png]]

Turn off all telemetry:
![[Pasted image 20251225212628.png]]

We wait...
![[Pasted image 20251225212653.png]]

And there it is!
![[Pasted image 20251225212811.png]]

I couldn't believe my eyes when I saw how much storage is being used:
![[Pasted image 20251225212841.png]]


Now, we don't have an internet connection so we need to go to  Device Manager, select Ethernet Controller and update the driver from our virtIO drive:
![[Pasted image 20251225213020.png]]

![[Pasted image 20251225213032.png]]

Browse -> VirtIODrivers -> NetKVM -> w11 -> amd64
![[Pasted image 20251225213123.png]]

And the drivers are now functional!
![[Pasted image 20251225213158.png]]

We have internet now!
![[Pasted image 20251225213246.png]]

And that's it for now.