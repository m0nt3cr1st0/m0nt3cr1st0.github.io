---
title: "Networking"
date: 2022-04-06T20:00:30+02:00
---

# Learning objectives

|           Learning Goal                        |                               Command                                            |
| ---------------------------------------------- | -------------------------------------------------------------------------------- |
| Configure networking and hostname resolution   | `ip` `nmcli` `hostnamectl` `nssitch.conf` `/etc/hosts` `/etc/resolv.conf` `FQDN` |
| Configure network services to start at boot    | `NetworkManager` `nmcli` `/etc/sysconfig/network-scripts`                        |
| Implement packet filtering                     | `firewalld` `firewall-cmd` `/usr/lib/firewalld/services`                         |
| Start/stop/check status of network services    | `NetworkManager` `network`                                                       |   
| Statically route IP traffic                    | `ip route` `/etc/sysconfig/network-scripts` `route` `/etc/sysctl.conf`   |
| Synchronize time using other network peers     | `date` `timedatectl` `chronyd` `chronyc`                                         |

# Extra commands that might come handy

* `lsof`
* `nc`

# Review questions

* Identify the ports that a specific process is using
* Print the routing table of the host

# TODO

* Make list prettier
* Make each item of the list a link to a different post
* Link to conceptual articles
