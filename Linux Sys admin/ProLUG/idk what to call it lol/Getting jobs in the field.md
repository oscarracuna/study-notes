
```
https://www.youtube.com/watch?v=Ao0ggeOhYdA
```
Based on job postings what are the skills you need to get a job as a linux sys admin?

- Diagnose and resolve issues related to Linux RHEL device management during standard business hours.
	1. pci devices `lspci` and then `dmsg | grep -i pci`
	2. network modules `lsmod | grep -i <something>`
	   `ethtool <name of interface> | grep -i "link detected"` 

- Regularly monitor the performance of Linux systems using various monitoring tools
	1. Big 4: CPU, Memory, Disk (Space, I/O), Network.
	   While loops `while true; do uptime; sleep 2; clear; done`
	   Tools (`iostat, sar`)
	   External monitoring tools (`Nagios, Zabbix, Grafana)

- Advanced server scripting abilities using bash, Perl and/or Python
	- Bash = interface with Linux
		- stdin, stdout, stderr
	- Perl = text transformation
	- Python - Ansible - Automated tasks