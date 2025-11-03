
This lifecycle describes how attacks manifest themselves. Understanding this lifecycle will provide us with valuable insights on how far in the network an attacker is and what they may have access to during the investigation phase of an incident.

The cyber kill chain consists of 7 different stages:
![[Pasted image 20250301112110.png]]

## Recon
It's the initial stage. It involves the part where an attacker chooses their target. They perform [[information gathering]]. Some attackers prefer to perform passive information gathering from web sources such as LinkedIn and Instagram but also from documentation on the target organization's web pages.

## Weaponize
The [[Malware]] to be used for the initial access is developed and embedded into some type of exploit or deliverable payload. It's designed to be extremely lightweight and undetectable by the [[antivirus]] and detection tools. It's likely the attacker has gathered information to identify the present antivirus or [[EDR]] technology in the target environment.

## Delivery
Here the exploit or payload is delivered to the victim. Traditional approaches are [[Phishing]] emails that either contain a malicious attachment or a link to a web page. The web page can be twofold: either containing an exploit or hosting the malicious payload to avoid sending it through email scanning tools.

## Exploitation
This is the moment when an exploit or a delivered payload is triggered. Here, the attacker typically attempts to execute code on thee target system in order to gain access or control.

## Installation
The initial stage is executed and is running on the compromised machine. It can be carried out in various ways, depending on the attacker's goals and the nature of the compromise. Some common technique used in the installation stage include:
- Droppers: Attackers may use droppers to deliver malware onto the target system. A [[dropper]] is a small piece of code that is designated to install malware on the system and execute it.
- [[Backdoor]]: This is a type of malware that is designed to provide the attacker with ongoing access to the compromised system. The backdoor may be installed by the attacker during the exploitation stage or delivered through a dropper. Once installed, the backdoor can be used to execute further attacks or steal data from the compromised system.
- [[Rootkit]]: Type of malware designed to hide its presence on a compromised system. Often used in the installation stage to evade detection by antivirus software and other security tools. The rootkit may be installed by the attacker during the exploitation stage or delivered through a dropper.

## [[Command and Control]] ([[C2]])
Here, the attacker establishes a remote access capability to the compromised machine. Advanced groups will utilize separate tools in order to ensure that multiple variants of their malware live in a compromised network.

## Action
Final stage.The objective of each attack may vary. Some may go for exfiltrating confidential data, others may want to obtain the highest level of access possible within a network to deploy [[ransomware]].