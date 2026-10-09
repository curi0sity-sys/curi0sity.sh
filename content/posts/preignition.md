+++ 
draft = false
date = 2026-10-09T13:42:20+02:00
title = "preignition"
description = ""
slug = ""
authors = []
tags = []
categories = ["starting point"]
externalLink = ""
series = []
+++

## Introduction.

We nmap the machine to get the open ports and running services.
```
nmap -sV 10.129.33.49
Starting Nmap 7.99 ( https://nmap.org ) at 2026-10-09 07:46 -0400
Nmap scan report for 10.129.33.49
Host is up (0.013s latency).
Not shown: 999 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
80/tcp open  http    nginx 1.14.2

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.19 seconds
```

Opening up the web page on port 80 we see the following:

