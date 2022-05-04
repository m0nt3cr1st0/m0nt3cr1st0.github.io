---
title: "Essential Commands"
date: 2022-04-06T20:00:30+02:00
---

# Foreword

The aim of this guide is to provide the quickest path possible towards passing the LFCS exam.
The way you are evaluated in this exam is based on practical exercises, so that's where I put the
focus on with these guides.

If you are a newcomer to Linux, I beg you to not stop here, Operating Systems is an amazing subject.
Its history is full of bright engineers who came up with clever solutions that you use on your day to day life. Take a full dive on other articles about the concepts these commands use here.

# Learning objectives

| Learning Goal      | Command     |
| ------------------ | ----------- |
| Log into local & remote txt consoles   | `ssh-keygen` `ssh-copy-id` `screen` `script`   |
| Search for files                       | `find`                                         |
| Compare & manipulate file content      | `diff` `md5sum`  `sed` `cut` `uniq` `sort`     |
| Use input-output redirection           | `<` `<<CHAR` `>` `>>` `2>` `&>` `tee` `mkfifo` |   
| Analyze text using basic RE            | `grep` `sed`                                   |
| Archive, backup, compress & viceversa  | `tar` `cpio` `dd`                              |
| Create, delete, cp, mv files & dirs    | `touch` `mkdir` `rm` `cp` `mv`                 |
| Create and manage hrd and sft links    | `ln` `ln -s`                                   |
| List, set and change std file perm     | `ls` `umask` `mkdir -m` `chmod` Suid, Guid, Stcky Bit | 
| Read and use system documentation      | `man` `info`                                          |
| Manage access to the root account      | `su` `sudo` `/etc/sudoers` `visudo` `PermitRootLogin` |

# Review Questions

1. Create a har file with 2048MB in the following location ~/lfcs-1/test/test2/
  1. Find the file looking by its type
  2. Find the file looking it by its size
  3. Find the file looking it by its name
  4. Find the file by looking it by its permissions
  5. Find the file by looking at its access time (less than 48h)
  6. Find the file by looking at who does NOT owns a file
  . Find the files that have a specific size or type
  . Find the file by any of the criteria above and copy it into /mnt
2. Find the difference between files
  1. Find the difference in case insensitive mode
3. Create a regex to find all the lines of a log file that start with a timestamp like this YYYY-MM-DD
  1. Create a regex to find and substitute all the dates YYYY-MM-DD to DD-MM-YYYY
  2. Create a regex to find all the lines that do not start with the # symbol and end with t, then substitute them by the word koala
4. Archive the content of the dir A into a tar file compressed by bzip algorithm
  1. Extract the file tar file into a new dir B
  2. Create a new file into dir B
  3. Make an incremental tar file from the previous tar file with the new file created
5. Extract the cpio image
  1. Make a new cpio archive
6. Make a block-by-block copy of a disk into another disk
7. Find an example of a file owned by root but that can't be deleted. Fix it's permission so it can be deleted
8. Explain the difference between the SETUID, GUID and the sticky bit.
  1. Set and unset each bit on a file. Then set/unset them in combinations of two
9. Verify the defaut umask value
  1. Modify the umask value for a user
  2. Modify the umaks value for a specific directory
10. Modify the sudoers file to give a user A the ability to run commands without being prompted the password
  1. Modify the sudoers file to give user A the ability to run ls commands as user B 

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles
