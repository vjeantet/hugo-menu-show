+++
date = "2015-07-15T22:17:00+02:00"
draft = false
title = "Duplicity + Amazon S3"

[menu.main]
Name = "Duplicity - S3"
parent = "Backup"
+++


In this article we will setup automated backup using Duplicity and Amazon S3.

# Installation

Run following commands to install latest duplicity and python-boto library (duplicity needs it for Amazon S3).
```
apt-add-repository ppa:duplicity-team/ppa
apt-get update
apt-get install duplicity
apt-get install python-pip
pip install boto
```

# Amazon S3

## S3 Bucket

