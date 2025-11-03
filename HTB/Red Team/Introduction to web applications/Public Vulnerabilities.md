The most critical back end component vulns are those that can be attacked externally (external pentests).

[[Public CVE]]
Common Vulnerabilities and Exposures.
Many penetration testers also make proof of concept exploits to test whether a certain public vuln can be exploited and usually make these exploits available for public use, for testing and educational purposes.

Once we identify the web app version, we can look for public exploits for that version of the web app. We can utilize online exploit databases like Exploit DB, Rapid7 DB, Vulnerability Lab or in Kali searchsploit.

[[CVSS]]
Common Vulnerability Scoring System.
Open-source industry standard for assessing the severity of security vulnerabilities.
CVSS scores are based on a formula that uses several metrics like Base, Temporal and Environmental.
The NVD (National Vulnerability Database) provides CVSS scores for almost all known publicly disclosed vulns. The NVD does not factor in Temporal and Environmental metrics given that the former can change over time.