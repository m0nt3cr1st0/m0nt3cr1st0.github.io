---
title: "User and Group Management"
date: 2022-04-06T20:00:30+02:00
---

# Foreword

The aim of this guide is to provide the quickest path possible towards passing the LFCS exam.
The way you are evaluated in this exam is based on practical exercises, so that's where I put the
focus on with these guides.

If you are a newcomer to Linux, I beg you to not stop here, Operating Systems is an amazing subject.
Its history is full of bright engineers who came up with clever solutions that you use on your day to day life. Take a full dive on other articles about the concepts these commands use here.

# Learning objectives

|              Learning Goal                |                             Command                                   |
| ----------------------------------------- | --------------------------------------------------------------------- |
| Manage local user accounts                | `user[add|mod|del]` `passwd` `/etc/default/useradd`                   |
| Manage local groups                       | `/etc/group` `group[add|mod]` `usermod -G`                            |
| Manage system-wide environment profiles   | `/etc/[profile]` `~/.bash_profile` `~/.bashrc` `/etc/bashrc` `source` |
| Manage template user environment          | `/etc/skel/` `/etc/login.defs`                                        |   
| Configure user resource limits            | `ulimit` `/etc/security/limits.conf`                                  |
| Manage user privileges                    | ??                                                                    |
| Configure PAM                             | `/etc/pam.d` `/lib[64]/security` `/etc/security`  |

# Review questions

1. Create a user called tux with password 'tux' and the csh as shell
  1.1 Set a expiration date of 2 months
  1.2 Change it's shell to bash
  1.3 Change default shell all new users get
2. Create a new group called penguins
  2.1 Add tux to the users penguins
  2.2 Find your newly create group penguins in a system config file
3. In which order environment profiles get read?
  3.1 Add an `echo` command to both the profile and the rc files of a specific user. Now use su to switch to that user
  Were you right about the order in which files are sourced? What happens if you use `su ` rather than `su -l`
  3.2 In which circumstance rc files are not sourced?
  3.3 Why do you need to export variables defined in your profile files?
4. Modify the necessary configuration files so all new users have nano aliased to vim
5. Modify the maximum amount of user processes your current session can SPAM
  5.1 Make this change persistant across reboots
  5.2 Make this change for all of the users of a specific group
6. PAM Question?

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles
