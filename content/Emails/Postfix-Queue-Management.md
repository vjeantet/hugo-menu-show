+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Postfix Queue Management"

[menu.main]
Name = "Postfix Queue Management"
parent = "Emails"
+++


Goal: To find which mails are stuck in mail queue and why?

If emails are getting delayed, its better to inspect postfix mail queues, coupled with postfix mail log.

# Status/Shape of Mail Queue

Postfix maintains different queues for different purpose.active  and  deferred queues are of our interest.

Ideally, we should never have a mail

