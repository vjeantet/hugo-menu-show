+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "DKIM with Postfix"


[menu.main]
Name = "DKIM with Postfix"
parent = "Emails"
+++


If mails from your web-server/webapp is having delivery issues, DKIM (DomainKeys Identified Mail) can help you big time.

Its highly recommended to use DKIM for outgoing emails even if your server is not running any kind of mail-hosting.

# Install DKIM

```apt-get install opendkim opendkim-tools```

# Edit