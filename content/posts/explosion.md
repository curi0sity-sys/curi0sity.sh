+++ 
draft = true
date = 2026-10-09T13:26:35+02:00
title = "explosion"
description = ""
slug = ""
authors = []
tags = []
categories = ["starting point"]
externalLink = ""
series = []
+++

## Introduction

We nmap the machine to get the open ports and running services.
```
nmap -sV 10.129.33.36     
Starting Nmap 7.99 ( https://nmap.org ) at 2026-10-09 07:32 -0400
Nmap scan report for 10.129.33.36
Host is up (0.013s latency).
Not shown: 995 closed tcp ports (reset)
PORT     STATE SERVICE       VERSION
135/tcp  open  msrpc         Microsoft Windows RPC
139/tcp  open  netbios-ssn   Microsoft Windows netbios-ssn
445/tcp  open  microsoft-ds?
3389/tcp open  ms-wbt-server Microsoft Terminal Services
5985/tcp open  http          Microsoft HTTPAPI httpd 2.0 (SSDP/UPnP)
Service Info: OS: Windows; CPE: cpe:/o:microsoft:windows

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 8.77 seconds
```

```
xfreerdp /v:10.129.33.36 /u:Administrator
```

flag is on the desktop.