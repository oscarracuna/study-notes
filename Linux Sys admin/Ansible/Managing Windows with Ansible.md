
I remember when I found out Ansible could be used to manage Windows endpoints. I wanted to immediately implement this at work. LOL

Anyway...

We're going to need a couple of things to get this running.
- Windows endpoint with winrm enabled.
- Allow winrm on Windows Firewall.
- pywinrm, evil-winrm or a tool that allows your Linux node to establish a winrm connection.
- For my use case, I installed ntlm for authentication, but for enterprise environments, a more sophisticated protocol will be needed.
- And that's about it.

My current host.yml looks like this:
![[Pasted image 20260212200337.png]]

I did not have the `ansible_winrm_scheme` and `ansible_port` sections so the connection was defaulting to https so I had to explicitly ask for http.

On my Windows endpoint I just had to run these commands to set up winrm:

```
winrm quickconfig
```

```
winrm set winrm/config/service/auth '@{Basic="true"}'
```

```
winrm set winrm/config/service '@{AllowUnencrypted="true"}'
```

```
Enable-NetFirewallRule -Name "WINRM-HTTP-In-TCP"
```

And that's it!


Documentation:
```
https://docs.ansible.com/projects/ansible/latest/os_guide/windows_winrm.html
```

Cool table:
![[Pasted image 20260212200833.png]]