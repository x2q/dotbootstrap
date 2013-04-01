---
layout: post
published: true
title: Smart informations
permalink: /smart-informations/
wordpress_id: 124
categories:
- News
---


Today I installed the <a href="http://sourceforge.net/apps/trac/smartmontools/wiki">smartmontools</a> package on a Debian server to read out some hard disk statistics.

Here is what I got out
<blockquote>
debian23:~# smartctl -a /dev/hda
SMART Attributes Data Structure revision number: 16
Vendor Specific SMART Attributes with Thresholds:
ID# ATTRIBUTE_NAME          FLAG     VALUE WORST THRESH TYPE      UPDATED  WHEN_FAILED RAW_VALUE
  1 Raw_Read_Error_Rate     0x000b   100   100   060    Pre-fail  Always       -       0
  2 Throughput_Performance  0x0005   100   100   050    Pre-fail  Offline      -       0
  3 Spin_Up_Time            0x0007   106   106   024    Pre-fail  Always       -       152 (Average 158)
  4 Start_Stop_Count        0x0012   100   100   000    Old_age   Always       -       68
  5 Reallocated_Sector_Ct   0x0033   100   100   005    Pre-fail  Always       -       0
  7 Seek_Error_Rate         0x000b   100   100   067    Pre-fail  Always       -       0
  8 Seek_Time_Performance   0x0005   100   100   020    Pre-fail  Offline      -       0
  9 Power_On_Hours          0x0012   098   098   000    Old_age   Always       -       14647
 10 Spin_Retry_Count        0x0013   100   100   060    Pre-fail  Always       -       0
 12 Power_Cycle_Count       0x0032   100   100   000    Old_age   Always       -       67
192 Power-Off_Retract_Count 0x0032   100   100   050    Old_age   Always       -       68
193 Load_Cycle_Count        0x0012   100   100   050    Old_age   Always       -       68
194 Temperature_Celsius     0x0002   152   152   000    Old_age   Always       -       36 (Lifetime Min/Max 20/56)
196 Reallocated_Event_Count 0x0032   100   100   000    Old_age   Always       -       0
197 Current_Pending_Sector  0x0022   100   100   000    Old_age   Always       -       0
198 Offline_Uncorrectable   0x0008   100   100   000    Old_age   Offline      -       0
199 UDMA_CRC_Error_Count    0x000a   200   200   000    Old_age   Always       -       0
</blockquote>


Very nice. As you can see the disk has been turned on 14647 hours almost 1.6 year and the temperature in the disk is 36 Celcius.
