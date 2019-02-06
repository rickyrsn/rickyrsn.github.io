---
layout: post
title: Script Auto Backup Mikrotik
date: 2019-02-06 11:30:00 +0700
---

#### via Winbox
- Open Winbox
- Navigate to System - Script
- Create New Script

Script: 
> :local tgl [:pick [/system clock get date] 4 6] <-- Pick Date  
:local bln [:pick [/system clock get date] 0 3] <-- Pick Month  
:local thn [:pick [/system clock get date] 7 11] <-- Pick Year  
/system backup save name="RB850Gx2 - $tgl $bln $thn"; <-- .backup  
/export file="RB850Gx2 - $tgl $bln $thn"; <-- .rsc

