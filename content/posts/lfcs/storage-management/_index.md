---
title: "Storage management"
date: 2022-04-06T20:00:30+02:00
---

# Foreword

The aim of this guide is to provide the quickest path possible towards passing the LFCS exam.
The way you are evaluated in this exam is based on practical exercises, so that's where I put the
focus on with these guides.

If you are a newcomer to Linux, I beg you to not stop here, Operating Systems is an amazing subject.
Its history is full of bright engineers who came up with clever solutions that you use on your day to day life. Take a full dive on other articles about the concepts these commands use here.

# Learning objectives

|               Learning Goal                 |               Command                        |
| ------------------------------------------- | -------------------------------------------- |
| Manage physical storage partitions          | `fdisk`                                      |
| Manage and configure LVM storage            | `{vg|pv|lv}create` `{pv|lv}resize`           |
| Create and configure encrypted storage      | `cryptsetup [luksFormat|luksOpen|luksClose]` |
| Configure and manage swap space             | `mkswap` `swap [on|off]` `/etc/sysctl.conf`  |
| Create and manage RAID devices              | `mdadm` `mdadm [--scan|--assemble]`          |
| Create and configure FS                     | `makefs.{xfs|ext4}`                          |
| Configure filesystems to be mounted on boot | `/etc/fstab`                                 |   
| Mount filesystems on demand                 | `mount`                                      |
| Setup user/group disk quotas for FS         | `quotacheck` `edquota` `repquota`            |
| Create and manage advanced FS permissions   | `getfacl` `setfacl`                          |


# Review Questions

1. Create a SWAP partition that is mount on boot
2. Same but using a SWAP file instead
3. Modify Swappiness value of the system
4. Create a software RAID-6 from two partitions
  1. Once the RAID is create save its config
  2. Destroy the created RAID
  3. Re-create it from the config of step 4.1
  4. Add a new spare device to the RAID
  5. Expand the RAID with the new device
  6. Remove the device from the RAID
1. Create two 200 MB partitions of type raid (fd) either on your hard disk using fdisk, or using LVM.
2. Create a RAID 1 device named /dev/md0 using the two partitions.
3. Format the RAID device as an ext4 filesystem. Then mount it at /myraid and make the mount persistent.
4. Place the information about /dev/md0 in /etc/mdadm.conf , using mdadm
5. Examine /proc/mdstat to see the status of your RAID device
5. Setup an encrypted partition
  1. Create a FS in that partition
  2. COnfigure the encrypted partition to be mounted on boot
6. Add a quota to a specific FS for a specific user
  1. Make that quota persistant across reboots
7. Create new ACL that allows only the user bob to read and write a file
  1. Make that ACL the default option
  2. Remove the default entry
  3. Remove all the entries
  4. Get the ACL of the file
8. Create LVM LV from a VG consisnting on two PVs.
  1. Expand the LV by adding a new disk.
  2. Reduce the LV by removing the previously added disk

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles

