
# Intranet mail server
You will need `postfix` and `dovecot`.

Modify the `/etc/postfix/main.cf` file with this template:
```
myhostname = mail.local <-- replace this with your domain.com
mydomain = local <-- and of course this with com or your TLD
myorigin = $mydomain
inet_interfaces = all
inet_protocols = ipv4
mydestination = $myhostname, localhost.$mydomain, localhost, $mydomain
home_mailbox = Maildir/
smtpd_banner = $myhostname ESMTP
mynetworks = 127.0.0.0/8
relay_domains = $mydestination
```

Now configure the mail_location on the 10-mail.conf file. It has to point to a specific directory, which can be in the home directory of the users. See example.
`/etc/dovecot/conf.d/10-mail.conf`
```
mail_location = maildir:~/Maildir
```
You can name the directory whatever you want, tho.

Now lets open ports 25(SMTP) and 143(IMAP).
```
sudo firewall-cmd --permanent --add-port=25/tcp
```
```
sudo firewall-cmd --permanent --add-port=143/tcp
```
```
sudo firewall-cmd --reload
```


And lastly, enable postfix and dovecot services:
```
sudo systemctl enable --now postfix dovecot
```


# Logging
You can use journalctl to see the logs:
```
sudo journalctl -u postfix -f | grep smtp
```
