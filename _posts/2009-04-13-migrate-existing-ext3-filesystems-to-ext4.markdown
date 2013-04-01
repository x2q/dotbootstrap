---
layout: post
published: true
title: Migrate existing Ext3 filesystems to Ext4
permalink: /migrate-existing-ext3-filesystems-to-ext4/
wordpress_id: 775
categories:
- News
- Linux
- Debian
- Ubuntu
- Fedora
- performance
- pdf
- Red Hat
- ext2
- ext3
- ext4
- Btrfs
- ext3 to ext4 migration
- debian ext4
- ext3 ext4 migration
- migration ext3 ext4
- migrate ext3 to ext4
- online defrag tool
- fsck tools
- software environment
- migrate ext3 ext4
---


Any existing Ext3 filesystem can be migrated to Ext4 with an easy procedure which consists in running a couple of commands in read-only mode (described in the next section). This means that you can improve the performance, storage limits and features of your current filesystems without reformatting and/or reinstalling your OS and software environment. If you need the advantages of Ext4 on a production system, you can upgrade the filesystem. The procedure is safe and doesn't risk your data (obviously, backup of critical data is recommended, even if you aren't updating your filesystem :). Ext4 will use the new data structures only on new data, the old structures will remain untouched and it will be possible to read/modify them when needed. This means, that, of course, that once you convert your filesystem to Ext4 you won't be able to go back to Ext3 again (although there's a possibility, described in the next section, of mounting a Ext3 filesystem with Ext4 without using the new disk format and you'll be able to mount it with Ext3 again, but you lose many of the advantages of Ext4).

<strong>Migrate a ext3 filesystem to ext4</strong>
You need to use the tune2fs and fsck tools in the filesystem, and that filesystem needs to be unmounted. Run:

# tune2fs -O extents,uninit_bg,dir_index /dev/sda1

After running this command you must run fsck. If you don't do it, Ext4 will NOT be able to mount your filesystem. This fsck run is needed to return the filesystem to a consistent state. It WILL tell you that it finds checksum errors in the group descriptors - it's expected, and it's exactly what it needs to be rebuilt to be able to mount it as Ext4, so don't get surprised by them. Since each time it finds one of those errors it asks you what to do, always say YES. If you don't want to be asked, add the "-p" parameter to the fsck command, it means "automatic repair":

# fsck -pDf /dev/sda1

There's another thing that must be mentioned. All your existing files will continue using the old indirect mapping to map all the blocks of data. The online defrag tool will be able to migrate each one of those files to a extent format (using a ioctl that tells the filesystem to rewrite the file with the extent format; you can use it safely while you're using the filesystem normally)
