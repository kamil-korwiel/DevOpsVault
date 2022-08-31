# Permissions
The best way learn permission in Linux is using command `ls -l` this command show us content of the directory `dev`
with long format to see most important information about files
``` shell
ls -l /dev

crw-r--r--  1 root     root       10, 235 sie 24 10:43 autofs
drwxr-xr-x  2 root     root           420 sie 24 10:43 block
lrwxrwxrwx  1 root     root            12 sie 24 10:43 initctl -> /run/initctl
brw-rw----  1 root     disk        7,   2 sie 24 10:43 loop2
crw-rw-r--+ 1 root     root       10, 242 sie 24 10:43 rfkill
drwxrwxrwt  2 root     root            40 sie 24 10:45 shm
-rw-rw-r--  1 confused confused       419 lip 29 17:29 extencion.txt
...
```

``` 
-rw-rw-r--  1 confused confused       419 lip 29 17:29 extencion.txt
↑___________________________________________________________________
```

-   `-` - Regular file.
-   `b` - Block special file.
-   `c` - Character special file.
-   `d` - Directory.
-   `l` - Symbolic link.
-   `n` - Network file.
-   `p` - FIFO.
-   `s` - Socket.

``` 
-rw-rw-r--  1 confused confused       419 lip 29 17:29 extencion.txt
_↑↑↑↑↑↑↑↑↑__________________________________________________________
```
`user – group – other`
-   `r` - Permission to read the file.
-   `w` - Permission to write to the file.
-   `x` - Permission to execute the file.
-   `s` - `setgid` bit.
-   `t` - `sticky` bit.
---
`chmod` - to change premonitions of file
`chown` - to change owner of file
`chgrp` - to change group of file
