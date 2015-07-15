+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Mailserver Port Numbers"


[menu.main]
Name = "Mailserver Port Numbers"

parent = "Emails-serversetup"
+++

Following are port numbers for different services:

* SMTP – 25 (465 with SSL, 587 with TLS)
* POP3 – 110 (995 for SSL)
* IMAP – 143 (993 for SSL)
* ManageSieve – 4190 (Gmail-like mail filtering)
* Amavis – 10025 (spam/antivirus checks)

You can find/verify ports used by postfix and dovecot using following commands:

```netstat -tulpn | egrep 'master|dovecot'```
