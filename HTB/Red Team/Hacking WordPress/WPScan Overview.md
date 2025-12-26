
WPScan is an automated [[WP]] scanner and enumeration tool. It determines if the various themes and plugins used by a [[Wordpress]] site are outdated or vulnerable. 

```shell
Rhaenesis@htb[/htb]$ wpscan --hh
_______________________________________________________________
         __          _______   _____
         \ \        / /  __ \ / ____|
          \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
           \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
            \  /\  /  | |     ____) | (__| (_| | | | |
             \/  \/   |_|    |_____/ \___|\__,_|_| |_|

         WordPress Security Scanner by the WPScan Team
                         Version 3.8.1
                               
       @_WPScan_, @ethicalhack3r, @erwan_lr, @firefart
_______________________________________________________________

Usage: wpscan [options]
        --url URL                                 The URL of the blog to scan
                                                  Allowed Protocols: http, https
                                                  Default Protocol if none provided: http
                                                  This option is mandatory unless update or help or hh or version is/are supplied
    -h, --help                                    Display the simple help and exit
        --hh                                      Display the full help and exit
        --version                                 Display the version and exit
        --ignore-main-redirect                    Ignore the main redirect (if any) and scan the target url
    -v, --verbose                                 Verbose mode
        --[no-]banner                             Whether or not to display the banner
                                                  Default: true
        --max-scan-duration SECONDS               Abort the scan if it exceeds the time provided in seconds
    -o, --output FILE                             Output to FILE
    -f, --format FORMAT                           Output results in the format supplied
                                                  Available choices: cli-no-colour, cli-no-color, json, cli
		<SNIP>
```

There are various enumeration options that can be specified such as vulnerable plugins, all plugins, [[User Enumeration]] and more.

WPScan can pull in vulnerability information form external sources to enhance our scans. We can obtain an API token from ``WPVulnDB`` which is used by WPScan to scan for vulnerabilities and exploit [[POC]] and reports. Use the --api-token parameter