+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Sieve Mail Filtering Setup"

[menu.main]
Name = "Sieve Mail Filtering Setup"
parent = "Emails-serversetup"
+++

This article covers:

Email filtering e.g. showing trash can to newsletters who do not honor unsubscribe links automatically. This is like Gmail filters.
Global spam filtering e.g. moving spam from inbox to junk folder (automatically)
# Installing packages for sieve and managesieve

We are using dovecot pigeonhole project for sieve support.

```apt-get install dovecot-sieve dovecot``