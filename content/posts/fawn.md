+++
draft = false
date = 2026-07-22T14:46:03+02:00
title = "fawn"
description = ""
slug = ""
authors = []
tags = []
categories = ["starting point"]
externalLink = ""
series = []
+++
![](/fawn/fawn.png)

# Fawn

Nmap:

```bash 
nmap -sV 10.129.131.99
Starting Nmap 7.99 ( https://nmap.org ) at 2026-07-31 16:20 +0200
Nmap scan report for 10.129.131.99
Host is up (0.011s latency).
Not shown: 999 closed tcp ports (conn-refused)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
Service Info: OS: Unix

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 3.04 seconds
```

Only FTP open.

Following the common misconfiguration of vsftpd, we can try to connect to the FTP server and see if we can find any interesting files or directories.

The anonymous FTP login is enabled.

Logging in with it, gives us the user flag.txt file.

