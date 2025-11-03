
Uncomplicated Firewall

Gotta have logging enabled.
You can check the current logging status with:

```
sudo ufw status verbose
```

Under "Logging", it should now say "on (low)".

The logging level controls how much detail is captured:

- **Low** – Blocked and allowed traffic only
- **Medium** – Adds unmatched connections
- **High** – Includes rate limited traffic
- **Full** – All traffic without rate limiting

For example, to enable the most verbose logging:

```
sudo ufw logging full
```


## How to log

Location:
/var/log/ufw.log

Older logs are number. ufw.log.1,ufw.log.2,ufw.log.3, etc.

So you can run:
```shell
sudo ls -l /var/log/ufw*
```

To monitor in real time:
```shell
sudo tail -f /var/log/ufw.log
```

