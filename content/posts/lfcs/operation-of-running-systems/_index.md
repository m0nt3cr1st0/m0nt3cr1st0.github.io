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
| Boot, reboot, and shut down a system safely          | `shutdown`                                                           |
| Boot or change system into different operating modes | `systemctl isolate|set-default` `/usr/lib/systemd/system/*.target`   |
| Install, configure and troubleshoot bootloader       | `grub2-[install|mkconfig]` `/etc/grub` `grubby`                      |
| Manage the startup process and services              | `systemctl` `/etc/systemd/system/` `UNIT-files format`               |
| Diagnose and manage processes                        | `ps` `/proc` `kill` `p(grep|kill)` `[re]nice` `jobs` `fg`            |
| Verify the integrity & availability of key processes | Same as above + `systemctl status process`                           |
| Locate and analyze system log files                  | `/var/log/` `/etc/rsyslog.conf` `/etc/logrotate.conf`                |
| Schedule tasks to run at a set date and time         | `crond` `/etc/cron.d` `anacron` `at`                                 |
| Use scripting to automate system maintenance tasks   | BASH + `crond`                                                       |
| Verify completion of scheduled jobs                  | `/var/log/cron`                                                      |
| Verify the integrity & availability of resources     | `rpm -V`                                                             | 
| Change kernel runtime parameters, (non-)persistent   | `/etc/sysctl.conf` `/etc/sysctl.d` `sysctl`                          |
| Manage Software                                      | `dnf [info|list|install|repolist]` `/etc/yum.repos.d` `rpm`          |
| Update software packages                             | `dnf check-updates` `dnf update`                                     |
| Identify the package that a file belongs to          | `rpm -qf`                                                            |
| Identify SELinux/AppArmor file and process contexts  | `-Z` `chcon` `restorecon` `semanage` `audit2[allow|why]` `semodule`  |

# Review questions

1. Switch the current run-level to the multi-user level
  1. make the previous change persistant
  2. make this change persistant through the bootloader
2. Install GRUB bootloader on a new partition
  1. Make a configuration change and re-install the bootloader
3. Find out if a service is running
  1. Create a ls service that uses netcat to listen for connections on a choosen port
  2. Make this new service to start on boot
  3. Show the dependencies of a service
  4. Prevent the service to start without disabling it
4. For the service created on 3, find its PID
  1. Find how much CPU load and memory is consuming
  2. Find out which open files the process has
  3. Find out which ports the service is listening on
  4. Reduce the priority of this process
  5. Terminate the process with a SIGKILL signal
5. Locate the logs of the system where failed login attempts are registered
  1. Locate the logs where sudoers actiosn are registered
6. Create a periodic task that executes every weekday at 5AM
  1. Create a periodic task that executes every monday that it is the first day of the month at 0AM
  2. What's the difference between cron and anacron?
  3. Make an anacron file that starts a task 10 minutes after the system has started
7. Create a BASH script that for a given input, it changes all the s to v. The change is case sensitive
8. Verify the integrity of the RPM database
  1. Verify the integrity of a specific package
9. List all kernel modules
  1. Load a specific module from the previous list
  2. Find its location on the filesystem
  3. Change the maximum number of open files allowed
  4. Make this change permanent without rebooting the system
10. List all available packages that start with postgres
  1. List all available packages related to polkit
  2. Display all the information for one of them
  3. Install a random package
  4. Remove that package along all its dependencies
  5. Download the RPM package of a random package
  6. Use rpm and dnf to tell which package a file belongs to
  7. Show what files are included in a random package
  8. Show only the config files
  9. List all the dependencies of a package with RPM
11. Show all the libraries used by a command
  1. Rebuild the library cache
12. Browse the logs of all actions contrary to the SELinux policy
  1. Identify the current SELinux state
  2. Name the difference between the possible states
  3. Show the SELinux context of a file
  4. Show the SELinux context of a process
  5. Copy the SELinux context from one file to another
  6. Restore the previous context of the copied file
  7. What's the difference between SELinux Booleans and contexts?
  8. List all posible booleans
  9. Get the explanation of one of them
  10. Change permanently the value of one of them 
  11. What are SELinux ports?
  12. Show the type of port 22
  13. Add a port to a specific type
  14. Remove it
  15. Identify a process being blocked by SELinux
  16. Create a policy to avoid the errors discovered above
  17. Install the new policy

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles
