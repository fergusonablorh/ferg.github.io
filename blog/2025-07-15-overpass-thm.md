---
layout: post
title: "TryHackMe – Overpass (Linux PrivEsc)"
date: 2025-07-15
---

**Goal:** Escalate to root on Overpass  
**Tools used:** LinPEAS, `pspy64`, manual enumeration  
**Exploit:** Abusing writable cron jobs + weak file permissions

> The real lesson? Always double-check scheduled jobs in `/etc/cron.*` — a tiny misconfig gave me root.

## Walkthrough

1. Enumerated users and running processes.
2. Found a cron job that writes to a log file in `/tmp`, owned by me.
3. Created a reverse shell script and replaced the cron-executed file.
4. Waited... caught root shell.

## Takeaway

Automation is powerful, but misconfigured automation is exploitable.