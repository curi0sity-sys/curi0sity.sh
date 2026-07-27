+++ 
draft = false
date = 2026-07-22T14:46:03+02:00
title = "meow"
description = ""
slug = ""
authors = []
tags = []
categories = ["starting point"]
externalLink = ""
series = []
+++

![](/meow/meow-front.png)


## Nmapping
We start the box, and nmap it.

nmap:
```bash
nmap -sV 10.129.123.103
```

```terminaloutput
Starting Nmap 7.99 ( https://nmap.org ) at 2026-07-27 12:58 +0200
Nmap scan report for 10.129.123.103
Host is up (0.011s latency).
Not shown: 999 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
23/tcp open  telnet  Linux telnetd
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 13.21 seconds
```