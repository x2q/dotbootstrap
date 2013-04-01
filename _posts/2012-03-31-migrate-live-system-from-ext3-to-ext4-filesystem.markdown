---
layout: post
published: true
title: Migrate Live System From Ext3 to Ext4 Filesystem
permalink: /migrate-live-system-from-ext3-to-ext4-filesystem/
wordpress_id: 2002
categories:
- Linux
- Howto
- Debian
- Ubuntu
- performance
- convert
- SSD
- ext2
- ext3
- ext4
- filesystem
- Btrfs
- defrag
- Ubuntu 12.04
- migration
- e4defrag
- benchmarks
---


<h3>Why Convert to Ext4</h3>
<strong>Compatibility</strong>
Any existing Ext3 filesystem can be migrated to Ext4 with an easy procedure which consists in running a couple of commands in read-only mode (described in the next section). This means that you can improve the performance, storage limits and features of your current filesystems without reformatting and/or reinstalling your OS and software environment. If you need the advantages of Ext4 on a production system, you can upgrade the filesystem. The procedure is safe and doesn't risk your data (obviously, backup of critical data is recommended, even if you aren't updating your filesystem :). Ext4 will use the new data structures only on new data, the old structures will remain untouched and it will be possible to read/modify them when needed. This means, of course, that once you convert your filesystem to Ext4 you won't be able to go back to Ext3 again (although there's a possibility, described in the next section, of mounting an Ext3 filesystem with Ext4 without using the new disk format and you'll be able to mount it with Ext3 again, but you lose many of the advantages of Ext4).

<strong>Extents</strong>
The traditionally Unix-derived filesystems like Ext3 use an indirect block mapping scheme to keep track of each block used for the blocks corresponding to the data of a file. This is inefficient for large files, specially on large file delete and truncate operations, because the mapping keeps a entry for every single block, and big files have many blocks -> huge mappings, slow to handle. Modern filesystems use a different approach called "extents". An extent is basically a bunch of contiguous physical blocks. It basically says "The data is in the next n blocks". For example, a 100 MB file can be allocated into a single extent of that size, instead of needing to create the indirect mapping for 25600 blocks (4 KB per block). Huge files are split in several extents. Extents improve the performance and also help to reduce the fragmentation, since an extent encourages continuous layouts on the disk.

<strong>Performance and SSD Readiness</strong>
Phoronix got some performance benchmarks: <a href="http://www.phoronix.com/scan.php?page=article&item=btrfs_linux31_ssd&num=1">Testing EXT4 & Btrfs On A Serial ATA 3.0 SSD</a>, <a href="http://www.phoronix.com/scan.php?page=article&item=linux_33_btrfs&num=1">Linux 3.3 Kernel: Btrfs vs. EXT4</a>.


<h3>How to Migrate Existing Ext3 filesystems to Ext4</h3>
You need to use the tune2fs and fsck tools in the filesystem, and that filesystem needs to be unmounted. Run:


```

sudo tune2fs -O extents,uninit_bg,dir_index /dev/sdb1

```


After running this command you MUST run fsck. If you don't do it, Ext4 WILL NOT MOUNT your filesystem. This fsck run is needed to return the filesystem to a consistent state. It WILL tell you that it finds checksum errors in the group descriptors - it's expected, and it's exactly what it needs to be rebuilt to be able to mount it as Ext4, so don't get surprised by them. Since each time it finds one of those errors it asks you what to do, always say YES. If you don't want to be asked, add the "-p" parameter to the fsck command, it means "automatic repair":


```

sudo fsck -pDf /dev/sdb1

```


There's another thing that must be mentioned. All your existing files will continue using the old indirect mapping to map all the blocks of data. The online defrag tool will be able to migrate each one of those files to an extent format (using an ioctl that tells the filesystem to rewrite the file with the extent format; you can use it safely while you're using the filesystem normally).

Using e4defrag you are able to fully migrate and this reduces fragmentation and make all files on the filesystem use the direct mapping to the blocks of data. The e4defrag ensures more contiguous blocks and improves the file access speed.


```

sudo e4defrag -c /dev/sdb1

```
