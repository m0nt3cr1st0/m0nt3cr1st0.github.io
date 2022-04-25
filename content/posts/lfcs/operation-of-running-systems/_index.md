---
title: "Operation of Running Systems"
date: 2022-04-06T20:00:30+02:00
---

# Foreword

The aim of this guide is to provide the quickest path possible towards passing the LFCS exam.
The way you are evaluated in this exam is based on practical exercises, so that's where I put the
focus on with these guides.

If you are a newcomer to Linux, I beg you to not stop here, Operating Systems is an amazing subject.
Its history is full of bright engineers who came up with clever solutions that you use on your day to day life. Take a full dive on other articles about the concepts these commands use here.

# Learning objectives

|                  Learning Goal                       |               Command               |
| ---------------------------------------------------- | ----------------------------------- |
| Boot, reboot, and shut down a system safely          | `shutdown`                                                         |
| Boot or change system into different operating modes | `systemctl isolate|set-default` `/usr/lib/systemd/system/*.target` |
| Install, configure and troubleshoot bootloader       | `grub2-[install|mkconfig]` `/etc/grub` `grubby`                    |
| Manage the startup process and services              | `systemctl` `/etc/systemd/system/` `UNIT-files format`             |
| Diagnose and manage processes                        | `ps` `/proc` `kill` `p(grep|kill)` `[re]nice` `jobs` `fg`          |
| Verify the integrity & availability of key processes | Same as above                                                      |
| Locate and analyze system log files                  | `/var/log/` `/etc/rsyslog.conf` `/etc/logrotate.conf`              |
| Schedule tasks to run at a set date and time         | `crond` `/etc/cron.d` `anacron` `at`                               |
| Use scripting to automate system maintenance tasks   | BASH + `crond`                                                     |
| Verify completion of scheduled jobs                  | `/var/log/cron`                                                    |
| Verify the integrity & availability of resources     | `rpm -V`                                                           | 
| Change kernel runtime parameters, (non-)persistent   | `/etc/sysctl.conf` `/etc/sysctl.d` `sysctl`                        |
| Manage Software                                      | `dnf [info|list|install|repolist]` `/etc/yum.repos.d` `rpm`        |
| Update software packages                             | `dnf check-updates` `dnf update`                                   |
| Identify the package that a file belongs to          | `rpm -qf`                                                          |
| Identify SELinux/AppArmor file and process contexts  |   |

# Review questions

1. Switch the current run-level to the multi-user level
    1.1 make the previous change persistant
    1.2 make this change persistant through the bootloader
2. What's the difference between cron and anacron?
    2.1 Make a file for each of them
3. 

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles
