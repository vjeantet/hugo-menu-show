+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "POP Tests"

[menu.main]
Name = "POP Tests"
parent = "Emails-serversetup-test"
+++


# Connect to server
```
telnet example.com 110
openssl s_client -crlf -connect example:995
```

# POP Test Commands
```
USER admin@example.com
PASS password
STAT 
LIST
QUIT
```