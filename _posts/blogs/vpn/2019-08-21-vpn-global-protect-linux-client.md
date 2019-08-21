---
layout: post
title: VPN - GlobalProtect Linux VPN Client Installation and usages.
status: published
type: post
published: true
comments: true
category: blogs
tags: [vpn, global, protect, globalprotect, palo, alto, paloalto, client, installation, linux, ubuntu, debian, unix, PanGP]
date: 2019-08-21T00:00:00+05:30
share: true
excerpt: In this blog post you will learn, how to install the GlobalProtect linux VPN client and how to use it.
---

To find the latest package of GlobalProtect, obtain it from your IT administrator, or you can you below links to download old packages [here](https://software.dartmouth.edu/Linux/Connectivity/PanGPLinux-4.1.9-c3.tgz){:target="_blank"}

Once you download the package, open a terminal by pressing Ctrl+T and change directory to the downloads.

```

user@linuxhost:~$ cd Downloads
user@linuxhost:~/Downloads$ tar -xvf PanGPLinux-x.x.x.tgz

```

Change the file name as per your downloaded package version like - PanGPLinux-5.0.3.tgz

Now change directory to extracted folder and start the installation. you will find few files in the directory, select the appropriate file to install. (you will will debian files, rpm files and tgz file.) 
In my case, for ubuntu we used debian file.

```

user@linuxhost:~/Downloads$ cd PanGPLinux-5.0.3
user@linuxhost:~/Downloads/PanGPLinux-5.0.3$ sudo dpkg -i GlobalProtect_deb-5.0.3.0-10.deb

// or you can simpaly use

user@linuxhost:~$ sudo apt-get install GlobalProtect_deb-5.0.3.0-10.deb

``` 

Client will install in to "/opt/paloaltonetworks/globalprotect" and settings & profile information are saved in "$HOME/.globalprotect".

Congratulation, Installation has been done.

Now, How to use the GlobalProtect. Below are the commands that can be used with globalprotect.

```

collect-log            -- collect log information 
connect                -- connect to server 
disconnect             -- disconnect
disable                -- disable connection
import-certificate     -- import client certificate file
quit                   -- quit from prompt mode
rediscover-network     -- network rediscovery
remove-user            -- clear credential 
resubmit-hip           -- resubmit hip information
set-log                -- set debug level
show                   -- show information

```

How to connect the VPN?

-> Without interactive mode -  

```

user@linuxhost:~$ globalprotect connect --portal myportal.example.com

```

-> With interactive mode - 

```

user@linuxhost:~$ globalprotect
>> connect --portal myportal.example.com

```
Output will be like - 

```

Retrieving configuration...                                            
Disconnected
There is a problem with the security certificate, so the identity of 10.1.121.35 cannot be verified. Please contact the Help Desk for your organization to have the issue rectified.
Warning: The communication with 10.1.121.35 may have been compromised. We recommend that you do not continue with this connection.
Error details:Do you want to continue(y/n)?y
Retrieving configuration...                                            
Disconnected
10.1.121.35 - portal:local:Enter login credentials
username:YourUsername
Password:
Retrieving configuration...                                            
Discovering network...
Connecting...
Connected 

```

How to disconnect the VPN?

```

user@linuxhost:~$ globalprotect disconnect

```

How to check the status of the connection - 

```

user@linuxhost:~$ globalprotect show --status

```

Hope this helps