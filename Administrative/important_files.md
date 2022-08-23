
`/etc/passwd` 
---
---
This file is responsible to store all the Linux users,
``` file
root:x:0:0:root:/root:/bin/bash
confused:x:1000:1000:confused,,,:/home/confused:/usr/bin/zsh
```
`user : password : user id : group id : comment : home folder : shell`

---

`/etc/shadow`
---
---
this file contains all the hashed password with , you need root privilege to accessed
``` file
root:!:19183:0:99999:7:::
confused:$6$FGptFr3fbOnvwY/c$JaY3VwB5vzshII8Hs4lfg8c.SFEAk9iLQRBSRXmISviloLqsJvDsPr8Ei/NaZUkfiWiATbdbkTnNi35HxqYQB/:19183:0:99999:7:::
```

- `user :` -  
- `encrypted pasword :` -   
- `last pass change :` -   
- `min pass age :` -   
- `max pass age :` -   
- `warning period :` -   
- `inactivity period :` -   
- `expiration date :` -   
- `unused` -   

---

`etc/group`
---
---
This file contains all groups
``` file
sudo:x:27:confused
confused:x:1000:
```
`group name : password : group id : users`

---
`/etc/fstab`
---
---
This file is responsible to mount our volumes during the boot  

```
UUID=bda7f20f-0f5f-4fe3-ab23-9a83f2c3f4aa / ext4 errors=remount-ro 0 1  

```
`partition : folder : file-system type : mounting options : backup enable : disk check sequence`

---
`/etc/hosts`
---
---
File that you can map an IP address to a name, as we did in the DNS  
It is very useful when you are developing a web system and you don't want to type the IP address in the browser every time
``` file
127.0.0.1	localhost
127.0.1.1	d-mashine

# The following lines are desirable for IPv6 capable hosts
::1     ip6-localhost ip6-loopback
fe00::0 ip6-localnet
ff00::0 ip6-mcastprefix
ff02::1 ip6-allnodes
ff02::2 ip6-allrouters
```

---
`/etc/hostname`
---
---
This file stores machine's hostname -> If you want to change the hostname, you can just edit this file
``` file
d-mashine
```

---
`/etc/crontab`
---
---
This is main file responsible to manage the scheduled tasks
``` file
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
17 *	* * *	root    cd / && run-parts --report /etc/cron.hourly
25 6	* * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6	* * 7	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6	1 * *	root	test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
#

```


---
`/var/spool/cron/crontabs/`
---
---
USER manage the scheduled tasks
``` file

```

#ToDo 

---
`/etc/ssh/sshd_config`
---
---
The configuration file for SSH connections.
Formerly, we have a short part of the file, in which you are able to change the port, and define which IP addresses will listen for the connections:  
One important configuration in the preceding file, is in some cases, we are able to login in the server using the root user directly. But, it is not a good practice. However, it is not uncommon to see in an on-premises environment. In the cloud environment, it is never allowed, because everyone in the world can try to access with the root user.
``` file

```


---
