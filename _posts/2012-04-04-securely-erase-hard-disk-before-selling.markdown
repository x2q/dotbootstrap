---
layout: post
published: true
title: Securely Erase Hard Disk Before Selling
permalink: /securely-erase-hard-disk-before-selling/
wordpress_id: 2009
categories:
- Linux
- Open Source
- Howto
- Debian
- Ubuntu
- Fedora
- security
- OSX
- Apple
- howto
- unix
- hardware
- shred
- DBAN
---
If you are using GNU/Linux or any other UNIX, then you have a tool called <a href="http://en.wikipedia.org/wiki/Shred_(Unix)">shred</a> which can be used to wipe all the data from the hard disk or from a file.

Boot your device on a <a href="http://www.ubuntu.com/download/desktop">Ubuntu</a> or <a href="http://www.debian.org/CD/live/">Debian USB Live Image</a>. 


```

$ shred -vfz -n 30 /dev/sdb
cc@ea:~$ sudo shred -vfz -n 30 /dev/sdb
shred: /dev/sdb: pass 1/31 (random)...
shred: /dev/sdb: pass 1/31 (random)...616MiB/39GiB 1%
shred: /dev/sdb: pass 1/31 (random)...617MiB/39GiB 1%
shred: /dev/sdb: pass 1/31 (random)...1,1GiB/39GiB 3%
shred: /dev/sdb: pass 1/31 (random)...1,2GiB/39GiB 3%
shred: /dev/sdb: pass 1/31 (random)...1,7GiB/39GiB 4%
shred: /dev/sdb: pass 1/31 (random)...1,8GiB/39GiB 4%
shred: /dev/sdb: pass 1/31 (random)...2,0GiB/39GiB 5%
shred: /dev/sdb: pass 1/31 (random)...2,1GiB/39GiB 5%
shred: /dev/sdb: pass 1/31 (random)...2,4GiB/39GiB 6%
shred: /dev/sdb: pass 1/31 (random)...2,5GiB/39GiB 6%
shred: /dev/sdb: pass 1/31 (random)...3,0GiB/39GiB 7%
shred: /dev/sdb: pass 1/31 (random)...3,1GiB/39GiB 8%
shred: /dev/sdb: pass 1/31 (random)...3,5GiB/39GiB 9%
shred: /dev/sdb: pass 1/31 (random)...3,6GiB/39GiB 9%
shred: /dev/sdb: pass 1/31 (random)...4,0GiB/39GiB 10%
shred: /dev/sdb: pass 1/31 (random)...4,1GiB/39GiB 10%
shred: /dev/sdb: pass 1/31 (random)...4,6GiB/39GiB 12%
shred: /dev/sdb: pass 1/31 (random)...4,7GiB/39GiB 12%
shred: /dev/sdb: pass 1/31 (random)...5,1GiB/39GiB 13%
shred: /dev/sdb: pass 1/31 (random)...5,2GiB/39GiB 13%
shred: /dev/sdb: pass 1/31 (random)...5,6GiB/39GiB 14%
shred: /dev/sdb: pass 1/31 (random)...5,7GiB/39GiB 14%
shred: /dev/sdb: pass 1/31 (random)...6,1GiB/39GiB 15%
shred: /dev/sdb: pass 1/31 (random)...6,2GiB/39GiB 16%
shred: /dev/sdb: pass 1/31 (random)...6,6GiB/39GiB 17%
shred: /dev/sdb: pass 1/31 (random)...6,7GiB/39GiB 17%
shred: /dev/sdb: pass 1/31 (random)...7,2GiB/39GiB 18%
shred: /dev/sdb: pass 1/31 (random)...7,3GiB/39GiB 19%
shred: /dev/sdb: pass 1/31 (random)...7,7GiB/39GiB 20%
shred: /dev/sdb: pass 1/31 (random)...7,8GiB/39GiB 20%
shred: /dev/sdb: pass 1/31 (random)...8,2GiB/39GiB 21%
shred: /dev/sdb: pass 1/31 (random)...8,3GiB/39GiB 21%
shred: /dev/sdb: pass 1/31 (random)...8,8GiB/39GiB 23%
shred: /dev/sdb: pass 1/31 (random)...8,9GiB/39GiB 23%
shred: /dev/sdb: pass 1/31 (random)...9,3GiB/39GiB 24%
shred: /dev/sdb: pass 1/31 (random)...9,4GiB/39GiB 24%
shred: /dev/sdb: pass 1/31 (random)...9,9GiB/39GiB 25%
shred: /dev/sdb: pass 1/31 (random)...10GiB/39GiB 26%
shred: /dev/sdb: pass 1/31 (random)...11GiB/39GiB 28%
shred: /dev/sdb: pass 1/31 (random)...12GiB/39GiB 31%
shred: /dev/sdb: pass 1/31 (random)...13GiB/39GiB 33%
shred: /dev/sdb: pass 1/31 (random)...14GiB/39GiB 36%
shred: /dev/sdb: pass 1/31 (random)...15GiB/39GiB 39%
shred: /dev/sdb: pass 1/31 (random)...16GiB/39GiB 41%
shred: /dev/sdb: pass 1/31 (random)...17GiB/39GiB 44%
shred: /dev/sdb: pass 1/31 (random)...18GiB/39GiB 46%
shred: /dev/sdb: pass 1/31 (random)...19GiB/39GiB 49%
shred: /dev/sdb: pass 1/31 (random)...20GiB/39GiB 52%
shred: /dev/sdb: pass 1/31 (random)...21GiB/39GiB 54%
shred: /dev/sdb: pass 1/31 (random)...22GiB/39GiB 57%
shred: /dev/sdb: pass 1/31 (random)...23GiB/39GiB 59%
shred: /dev/sdb: pass 1/31 (random)...24GiB/39GiB 62%
shred: /dev/sdb: pass 1/31 (random)...25GiB/39GiB 65%
shred: /dev/sdb: pass 1/31 (random)...26GiB/39GiB 67%
shred: /dev/sdb: pass 1/31 (random)...27GiB/39GiB 70%
shred: /dev/sdb: pass 1/31 (random)...28GiB/39GiB 73%
shred: /dev/sdb: pass 1/31 (random)...29GiB/39GiB 75%
shred: /dev/sdb: pass 1/31 (random)...30GiB/39GiB 78%
shred: /dev/sdb: pass 1/31 (random)...31GiB/39GiB 80%
shred: /dev/sdb: pass 1/31 (random)...32GiB/39GiB 83%
shred: /dev/sdb: pass 1/31 (random)...33GiB/39GiB 86%
shred: /dev/sdb: pass 1/31 (random)...34GiB/39GiB 88%
shred: /dev/sdb: pass 1/31 (random)...35GiB/39GiB 91%
shred: /dev/sdb: pass 1/31 (random)...36GiB/39GiB 93%
shred: /dev/sdb: pass 1/31 (random)...37GiB/39GiB 96%
shred: /dev/sdb: pass 1/31 (random)...38GiB/39GiB 99%
shred: /dev/sdb: pass 1/31 (random)...39GiB/39GiB 100%
shred: /dev/sdb: pass 2/31 (555555)...
shred: /dev/sdb: pass 2/31 (555555)...553MiB/39GiB 1%
shred: /dev/sdb: pass 2/31 (555555)...554MiB/39GiB 1%
shred: /dev/sdb: pass 2/31 (555555)...1,0GiB/39GiB 2%
shred: /dev/sdb: pass 2/31 (555555)...1,1GiB/39GiB 2%
shred: /dev/sdb: pass 2/31 (555555)...1,6GiB/39GiB 4%
shred: /dev/sdb: pass 2/31 (555555)...1,7GiB/39GiB 4%
shred: /dev/sdb: pass 2/31 (555555)...2,1GiB/39GiB 5%
shred: /dev/sdb: pass 2/31 (555555)...2,2GiB/39GiB 5%
shred: /dev/sdb: pass 2/31 (555555)...2,6GiB/39GiB 6%
shred: /dev/sdb: pass 2/31 (555555)...2,7GiB/39GiB 7%
shred: /dev/sdb: pass 2/31 (555555)...3,1GiB/39GiB 8%
shred: /dev/sdb: pass 2/31 (555555)...3,2GiB/39GiB 8%
shred: /dev/sdb: pass 2/31 (555555)...3,7GiB/39GiB 9%
shred: /dev/sdb: pass 2/31 (555555)...3,8GiB/39GiB 9%
shred: /dev/sdb: pass 2/31 (555555)...4,2GiB/39GiB 11%
shred: /dev/sdb: pass 2/31 (555555)...4,3GiB/39GiB 11%
shred: /dev/sdb: pass 2/31 (555555)...4,7GiB/39GiB 12%
shred: /dev/sdb: pass 2/31 (555555)...4,8GiB/39GiB 12%
shred: /dev/sdb: pass 2/31 (555555)...5,3GiB/39GiB 13%
shred: /dev/sdb: pass 2/31 (555555)...5,4GiB/39GiB 14%
shred: /dev/sdb: pass 2/31 (555555)...5,8GiB/39GiB 15%
shred: /dev/sdb: pass 2/31 (555555)...5,9GiB/39GiB 15%
shred: /dev/sdb: pass 2/31 (555555)...6,3GiB/39GiB 16%
shred: /dev/sdb: pass 2/31 (555555)...6,4GiB/39GiB 16%
shred: /dev/sdb: pass 2/31 (555555)...6,8GiB/39GiB 17%
shred: /dev/sdb: pass 2/31 (555555)...6,9GiB/39GiB 17%
shred: /dev/sdb: pass 2/31 (555555)...7,4GiB/39GiB 19%
shred: /dev/sdb: pass 2/31 (555555)...7,5GiB/39GiB 19%
shred: /dev/sdb: pass 2/31 (555555)...7,6GiB/39GiB 19%
shred: /dev/sdb: pass 2/31 (555555)...7,7GiB/39GiB 20%
shred: /dev/sdb: pass 2/31 (555555)...7,8GiB/39GiB 20%
shred: /dev/sdb: pass 2/31 (555555)...8,3GiB/39GiB 21%
shred: /dev/sdb: pass 2/31 (555555)...8,4GiB/39GiB 21%
shred: /dev/sdb: pass 2/31 (555555)...8,8GiB/39GiB 23%
shred: /dev/sdb: pass 2/31 (555555)...8,9GiB/39GiB 23%
shred: /dev/sdb: pass 2/31 (555555)...9,3GiB/39GiB 24%
shred: /dev/sdb: pass 2/31 (555555)...9,4GiB/39GiB 24%
shred: /dev/sdb: pass 2/31 (555555)...9,9GiB/39GiB 25%
shred: /dev/sdb: pass 2/31 (555555)...10GiB/39GiB 26%
shred: /dev/sdb: pass 2/31 (555555)...11GiB/39GiB 28%
shred: /dev/sdb: pass 2/31 (555555)...12GiB/39GiB 31%
shred: /dev/sdb: pass 2/31 (555555)...13GiB/39GiB 33%
shred: /dev/sdb: pass 2/31 (555555)...14GiB/39GiB 36%
shred: /dev/sdb: pass 2/31 (555555)...15GiB/39GiB 39%
shred: /dev/sdb: pass 2/31 (555555)...16GiB/39GiB 41%
shred: /dev/sdb: pass 2/31 (555555)...17GiB/39GiB 44%
shred: /dev/sdb: pass 2/31 (555555)...18GiB/39GiB 46%
shred: /dev/sdb: pass 2/31 (555555)...19GiB/39GiB 49%
shred: /dev/sdb: pass 2/31 (555555)...20GiB/39GiB 52%
shred: /dev/sdb: pass 2/31 (555555)...21GiB/39GiB 54%
shred: /dev/sdb: pass 2/31 (555555)...22GiB/39GiB 57%
shred: /dev/sdb: pass 2/31 (555555)...23GiB/39GiB 59%
shred: /dev/sdb: pass 2/31 (555555)...24GiB/39GiB 62%
shred: /dev/sdb: pass 2/31 (555555)...25GiB/39GiB 65%
shred: /dev/sdb: pass 2/31 (555555)...26GiB/39GiB 67%
shred: /dev/sdb: pass 2/31 (555555)...27GiB/39GiB 70%
shred: /dev/sdb: pass 2/31 (555555)...28GiB/39GiB 73%
shred: /dev/sdb: pass 2/31 (555555)...29GiB/39GiB 75%
shred: /dev/sdb: pass 2/31 (555555)...30GiB/39GiB 78%
shred: /dev/sdb: pass 2/31 (555555)...31GiB/39GiB 80%
shred: /dev/sdb: pass 2/31 (555555)...32GiB/39GiB 83%
shred: /dev/sdb: pass 2/31 (555555)...33GiB/39GiB 86%
shred: /dev/sdb: pass 2/31 (555555)...34GiB/39GiB 88%
shred: /dev/sdb: pass 2/31 (555555)...35GiB/39GiB 91%
shred: /dev/sdb: pass 2/31 (555555)...36GiB/39GiB 93%
shred: /dev/sdb: pass 2/31 (555555)...37GiB/39GiB 96%
shred: /dev/sdb: pass 2/31 (555555)...38GiB/39GiB 99%
shred: /dev/sdb: pass 2/31 (555555)...39GiB/39GiB 100%
shred: /dev/sdb: pass 3/31 (924924)...
shred: /dev/sdb: pass 3/31 (924924)...541MiB/39GiB 1%
shred: /dev/sdb: pass 3/31 (924924)...542MiB/39GiB 1%
shred: /dev/sdb: pass 3/31 (924924)...1,0GiB/39GiB 2%
shred: /dev/sdb: pass 3/31 (924924)...1,1GiB/39GiB 2%
shred: /dev/sdb: pass 3/31 (924924)...1,5GiB/39GiB 4%
shred: /dev/sdb: pass 3/31 (924924)...1,6GiB/39GiB 4%
shred: /dev/sdb: pass 3/31 (924924)...2,1GiB/39GiB 5%
shred: /dev/sdb: pass 3/31 (924924)...2,2GiB/39GiB 5%
shred: /dev/sdb: pass 3/31 (924924)...2,6GiB/39GiB 6%
shred: /dev/sdb: pass 3/31 (924924)...2,7GiB/39GiB 7%
shred: /dev/sdb: pass 3/31 (924924)...3,1GiB/39GiB 8%
shred: /dev/sdb: pass 3/31 (924924)...3,2GiB/39GiB 8%
shred: /dev/sdb: pass 3/31 (924924)...3,6GiB/39GiB 9%
shred: /dev/sdb: pass 3/31 (924924)...3,7GiB/39GiB 9%
shred: /dev/sdb: pass 3/31 (924924)...4,2GiB/39GiB 11%
shred: /dev/sdb: pass 3/31 (924924)...4,3GiB/39GiB 11%
shred: /dev/sdb: pass 3/31 (924924)...4,7GiB/39GiB 12%
shred: /dev/sdb: pass 3/31 (924924)...4,8GiB/39GiB 12%
shred: /dev/sdb: pass 3/31 (924924)...5,2GiB/39GiB 13%
shred: /dev/sdb: pass 3/31 (924924)...5,3GiB/39GiB 13%
shred: /dev/sdb: pass 3/31 (924924)...5,7GiB/39GiB 15%
shred: /dev/sdb: pass 3/31 (924924)...5,8GiB/39GiB 15%
shred: /dev/sdb: pass 3/31 (924924)...6,2GiB/39GiB 16%
shred: /dev/sdb: pass 3/31 (924924)...6,3GiB/39GiB 16%
shred: /dev/sdb: pass 3/31 (924924)...6,8GiB/39GiB 17%
shred: /dev/sdb: pass 3/31 (924924)...6,9GiB/39GiB 17%
shred: /dev/sdb: pass 3/31 (924924)...7,3GiB/39GiB 19%
shred: /dev/sdb: pass 3/31 (924924)...7,4GiB/39GiB 19%
shred: /dev/sdb: pass 3/31 (924924)...7,8GiB/39GiB 20%
shred: /dev/sdb: pass 3/31 (924924)...7,9GiB/39GiB 20%
shred: /dev/sdb: pass 3/31 (924924)...8,3GiB/39GiB 21%
shred: /dev/sdb: pass 3/31 (924924)...8,4GiB/39GiB 21%
shred: /dev/sdb: pass 3/31 (924924)...8,9GiB/39GiB 23%
shred: /dev/sdb: pass 3/31 (924924)...9,0GiB/39GiB 23%
shred: /dev/sdb: pass 3/31 (924924)...9,4GiB/39GiB 24%
shred: /dev/sdb: pass 3/31 (924924)...9,5GiB/39GiB 24%
shred: /dev/sdb: pass 3/31 (924924)...9,9GiB/39GiB 25%
shred: /dev/sdb: pass 3/31 (924924)...10GiB/39GiB 26%
shred: /dev/sdb: pass 3/31 (924924)...11GiB/39GiB 28%
shred: /dev/sdb: pass 3/31 (924924)...12GiB/39GiB 31%
shred: /dev/sdb: pass 3/31 (924924)...13GiB/39GiB 33%
shred: /dev/sdb: pass 3/31 (924924)...14GiB/39GiB 36%
shred: /dev/sdb: pass 3/31 (924924)...15GiB/39GiB 39%
shred: /dev/sdb: pass 3/31 (924924)...16GiB/39GiB 41%
shred: /dev/sdb: pass 3/31 (924924)...17GiB/39GiB 44%
shred: /dev/sdb: pass 3/31 (924924)...18GiB/39GiB 46%
shred: /dev/sdb: pass 3/31 (924924)...19GiB/39GiB 49%
shred: /dev/sdb: pass 3/31 (924924)...20GiB/39GiB 52%
shred: /dev/sdb: pass 3/31 (924924)...21GiB/39GiB 54%
shred: /dev/sdb: pass 3/31 (924924)...22GiB/39GiB 57%
shred: /dev/sdb: pass 3/31 (924924)...23GiB/39GiB 59%
shred: /dev/sdb: pass 3/31 (924924)...24GiB/39GiB 62%
shred: /dev/sdb: pass 3/31 (924924)...25GiB/39GiB 65%
shred: /dev/sdb: pass 3/31 (924924)...26GiB/39GiB 67%
shred: /dev/sdb: pass 3/31 (924924)...27GiB/39GiB 70%
shred: /dev/sdb: pass 3/31 (924924)...28GiB/39GiB 73%
shred: /dev/sdb: pass 3/31 (924924)...29GiB/39GiB 75%
shred: /dev/sdb: pass 3/31 (924924)...30GiB/39GiB 78%
shred: /dev/sdb: pass 3/31 (924924)...31GiB/39GiB 80%
shred: /dev/sdb: pass 3/31 (924924)...32GiB/39GiB 83%
shred: /dev/sdb: pass 3/31 (924924)...33GiB/39GiB 86%
shred: /dev/sdb: pass 3/31 (924924)...34GiB/39GiB 88%
shred: /dev/sdb: pass 3/31 (924924)...35GiB/39GiB 91%
shred: /dev/sdb: pass 3/31 (924924)...36GiB/39GiB 93%
shred: /dev/sdb: pass 3/31 (924924)...37GiB/39GiB 96%
shred: /dev/sdb: pass 3/31 (924924)...38GiB/39GiB 99%
shred: /dev/sdb: pass 3/31 (924924)...39GiB/39GiB 100%
shred: /dev/sdb: pass 4/31 (a49249)...
shred: /dev/sdb: pass 4/31 (a49249)...537MiB/39GiB 1%
shred: /dev/sdb: pass 4/31 (a49249)...538MiB/39GiB 1%
shred: /dev/sdb: pass 4/31 (a49249)...1,0GiB/39GiB 2%
shred: /dev/sdb: pass 4/31 (a49249)...1,1GiB/39GiB 2%
shred: /dev/sdb: pass 4/31 (a49249)...1,5GiB/39GiB 4%
shred: /dev/sdb: pass 4/31 (a49249)...1,6GiB/39GiB 4%
shred: /dev/sdb: pass 4/31 (a49249)...2,1GiB/39GiB 5%
shred: /dev/sdb: pass 4/31 (a49249)...2,2GiB/39GiB 5%
shred: /dev/sdb: pass 4/31 (a49249)...2,6GiB/39GiB 6%
shred: /dev/sdb: pass 4/31 (a49249)...2,7GiB/39GiB 7%
shred: /dev/sdb: pass 4/31 (a49249)...2,8GiB/39GiB 7%
shred: /dev/sdb: pass 4/31 (a49249)...2,9GiB/39GiB 7%
shred: /dev/sdb: pass 4/31 (a49249)...3,0GiB/39GiB 7%
shred: /dev/sdb: pass 4/31 (a49249)...3,2GiB/39GiB 8%
shred: /dev/sdb: pass 4/31 (a49249)...3,3GiB/39GiB 8%
shred: /dev/sdb: pass 4/31 (a49249)...3,7GiB/39GiB 9%
shred: /dev/sdb: pass 4/31 (a49249)...3,8GiB/39GiB 9%
shred: /dev/sdb: pass 4/31 (a49249)...4,1GiB/39GiB 10%
shred: /dev/sdb: pass 4/31 (a49249)...4,2GiB/39GiB 10%
shred: /dev/sdb: pass 4/31 (a49249)...4,6GiB/39GiB 12%
shred: /dev/sdb: pass 4/31 (a49249)...4,7GiB/39GiB 12%
shred: /dev/sdb: pass 4/31 (a49249)...5,1GiB/39GiB 13%
shred: /dev/sdb: pass 4/31 (a49249)...5,2GiB/39GiB 13%
shred: /dev/sdb: pass 4/31 (a49249)...5,4GiB/39GiB 14%
shred: /dev/sdb: pass 4/31 (a49249)...5,5GiB/39GiB 14%
shred: /dev/sdb: pass 4/31 (a49249)...5,9GiB/39GiB 15%
shred: /dev/sdb: pass 4/31 (a49249)...6,0GiB/39GiB 15%
shred: /dev/sdb: pass 4/31 (a49249)...6,1GiB/39GiB 15%
shred: /dev/sdb: pass 4/31 (a49249)...6,2GiB/39GiB 16%
shred: /dev/sdb: pass 4/31 (a49249)...6,3GiB/39GiB 16%
shred: /dev/sdb: pass 4/31 (a49249)...6,8GiB/39GiB 17%
shred: /dev/sdb: pass 4/31 (a49249)...6,9GiB/39GiB 17%
shred: /dev/sdb: pass 4/31 (a49249)...7,0GiB/39GiB 18%
shred: /dev/sdb: pass 4/31 (a49249)...7,1GiB/39GiB 18%
shred: /dev/sdb: pass 4/31 (a49249)...7,5GiB/39GiB 19%
shred: /dev/sdb: pass 4/31 (a49249)...7,6GiB/39GiB 19%
shred: /dev/sdb: pass 4/31 (a49249)...8,0GiB/39GiB 21%
shred: /dev/sdb: pass 4/31 (a49249)...8,1GiB/39GiB 21%
shred: /dev/sdb: pass 4/31 (a49249)...8,6GiB/39GiB 22%
shred: /dev/sdb: pass 4/31 (a49249)...8,7GiB/39GiB 22%
shred: /dev/sdb: pass 4/31 (a49249)...9,1GiB/39GiB 23%
shred: /dev/sdb: pass 4/31 (a49249)...9,2GiB/39GiB 23%
shred: /dev/sdb: pass 4/31 (a49249)...9,6GiB/39GiB 25%
shred: /dev/sdb: pass 4/31 (a49249)...9,7GiB/39GiB 25%
shred: /dev/sdb: pass 4/31 (a49249)...10GiB/39GiB 26%
shred: /dev/sdb: pass 4/31 (a49249)...11GiB/39GiB 28%
shred: /dev/sdb: pass 4/31 (a49249)...12GiB/39GiB 31%
shred: /dev/sdb: pass 4/31 (a49249)...13GiB/39GiB 33%
shred: /dev/sdb: pass 4/31 (a49249)...14GiB/39GiB 36%
shred: /dev/sdb: pass 4/31 (a49249)...15GiB/39GiB 39%

```


This makes 30 passes by overwriting the entire hard disk with -z zeros.
