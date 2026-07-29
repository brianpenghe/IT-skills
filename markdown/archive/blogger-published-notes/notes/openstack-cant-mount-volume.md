---
title: 'Openstack can''t mount volume'
date: 2019-03-08T04:34:00.001-08:00
draft: false
url: /2019/03/openstack-cant-mount-volume.html
---

> **Archived note — originally created: 2019-03-08 — old (5–8 years) — verify carefully**  
> Imported from Obsidian `TroubleshootNotes/BloggerPublishedNonAcademicNotes`.  
> Older notes are often outdated or environment-specific; verify before following.

---


sudo mkfs.ext4 /dev/vdb

mke2fs 1.44.1 (24-Mar-2018)

The file /dev/vdb does not exist and no size was specified.

Solution:

sudo sed '/^\\/dev\\/vdb/ d' -i /etc/fstab sudo reboot & ( sleep 30; echo 'b' > /proc/sysrq-trigger )

sudo mkfs.ext4 /dev/vdb sudo mount /dev/vdb /mnt sudo chown -R ubuntu: /mnt cd /mnt && dd if=/dev/zero of=deleteme oflag=direct bs=1M count=1024 && rm deleteme

#TroubleshootNotes #BloggerPublishedNonAcademicNotes
