
My current set up uses a RHEL10 VM as the bastion node and also the control node for anything ansible.

## Current playbooks:

- firewall-default:
	- This one just sets up a basic UFW or Firewalld (depending on RHEL or Debian based), enabling the firewall, setting it up and allowing SSH. Deny everything and then I manually allow whatever I need.
- ssh_key_addition
	- I created this one to add the ssh key of my Proxmox host to all VMs, just in case.
- update_all_servers
	- Very self explanatory. It updates all endpoints. Uses apt for Debian based servers and dnf for RHEL based servers.
![[Pasted image 20260212195312.png]]
