---
title: "General notes"
draft: true
date: 2022-04-01
---


# Working with dirs

* mkdir -m MODE dirname

# Working with links

* Hard link another name for the same file/inode
* Soft link a pointer to a different file. different inode
* ls output shows hard links count, this is useful to know amount of files under 
a directory
* ln SRC TARGET

# Reading files
* less -> / ? + go bottom, go top
  * https://www.thegeekstuff.com/2010/02/unix-less-command-10-tips-for-effective-navigation/
* grep PATTERN FILE
  * download words package to practice
  * Use -E for extended regular expressions just in case
  * Build some regexp -> ^,$,{},[]
* sed
  * ; for concatenate commands -> sed -i `/^#/d;/^$/d` mytest
  * `/pattern/d`
  * `s/regexp/replacement` -> & indicates the matched regexp might come handy
* md5sum
* find
  * -maxdepth
  * -type
  * -size
  * -name
  * -o
  * -exec cmd -> `find /etc -name 'cacota' -exec cp {} . \;`
    * {} indicates the matched file
    * \ is needed to escape {}
    * ; is needed to indicate end of command
  * -ok is like exec but prompts before running the command for each matched file

# Text editors
* touch: changes access or modification time -> stat
* vim:
  ** vimsettings
  ** navigation
    ** $ + ^
    ** :e!
    ** yy + p

# Redirecting STDOUT + STDIN
* >, >>, 1>, 2>, &>, <, |
* Named pipes: mkfifo mypipe -> ls > mypipe; cat < mypipe
  * Cmd that put info on the pipe is blocked until the info is consumed
* `tee [FILE]`: read from STDIN and write to STDOUT + File
* HERE Documents: cat > file << END

# Archiving files
* `tar [-t|c|x] [-z|j] [-v]`
  * `-g` usefull for incr backups -> TO-DO make exercise
* `gzip` + `gunzip`
* `cpio -id`
* `dd -if -of -bs -count` -> TO-DO exercise: when to use `bs` and `count`

# File Permissions
* SetUID, GroupUID: run the binary with the privileges of the owner
* Stickybit: only the owner can delete files of that dir -> Ex. /tmp
  * Octal notation: XNNN
  * Regular notation: [u|g|w]+t
* `umask`
* `chmod`, `chown`, `chgrp` 

# Accessing the root account
* `su [-l]` -> without -l it doesn't change ENV 
* `sudo -iu [username]` -> without -i it doesn't change ENV
  * Controlled through `/etc/sudoers`
  * Format `user/group HOST|ALL=(user/group|ALL) CMDs`
    * `nagioschk     ALL=(root) NOPASSWD: /sbin/aureport --summary`
* Main diff between `su` and `sudo` -> 

# Accessing servers with SSH
* ssh-keygen
* ssh-copy-id

# Using screen and script

* Demo: making an interactive session with `script`
  1. Make a named pipe
  2. Run script providing the named pipe as the input -> `script -f mypipe`
  3. Open a different terminal window and read from the pipe -> `cat mypipe`
  4. That's it! Everything you do on the session where script was started should appear on the other session

* `screen [-S] [-list] [-r] session_name` -> <C-A> + <C-D>

