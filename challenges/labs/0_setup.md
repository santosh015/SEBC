### AWS information
<pre><code>
ap-southeast-1
CentOS-6.5-GA-03.3-f4325b48-37b0-405a-9847-236c64622e3e-ami-6be4dc02.2 (ami-a08fd9f2) with volumes resized to a 50GB
</code></pre>

### Disk space
<pre><code>
[root@ip-172-31-9-250 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvde        50G  658M   47G   2% /
tmpfs           7.4G     0  7.4G   0% /dev/shm
[root@ip-172-31-9-250 ~]#
</code></pre>

### My repository
<pre><code>
[root@ip-172-31-9-250 ~]# yum repolist enabled
Failed to set locale, defaulting to C
Loaded plugins: fastestmirror, presto
base                                                                                                                                               | 3.7 kB     00:00     
base/primary_db                                                                                                                                    | 4.7 MB     00:00     
extras                                                                                                                                             | 3.4 kB     00:00     
extras/primary_db                                                                                                                                  |  37 kB     00:00     
updates                                                                                                                                            | 3.4 kB     00:00     
updates/primary_db                                                                                                                                 | 3.7 MB     00:00     
repo id                                                                     repo name                                                                               status
base                                                                        CentOS-6 - Base                                                                         6696
extras                                                                      CentOS-6 - Extras                                                                         62
updates                                                                     CentOS-6 - Updates                                                                       686
repolist: 7444
[root@ip-172-31-9-250 ~]#

</code></pre>

### User added
<pre><code>
groupadd shops
groupadd walks
useradd -u 2700 -g walks raffles
useradd -u 2800 -g shops orchard
usermod -a -G walks raffles
usermod -a -G shops orchard

[root@ip-172-31-9-250 ~]# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
bin:x:1:1:bin:/bin:/sbin/nologin
daemon:x:2:2:daemon:/sbin:/sbin/nologin
adm:x:3:4:adm:/var/adm:/sbin/nologin
lp:x:4:7:lp:/var/spool/lpd:/sbin/nologin
sync:x:5:0:sync:/sbin:/bin/sync
shutdown:x:6:0:shutdown:/sbin:/sbin/shutdown
halt:x:7:0:halt:/sbin:/sbin/halt
mail:x:8:12:mail:/var/spool/mail:/sbin/nologin
uucp:x:10:14:uucp:/var/spool/uucp:/sbin/nologin
operator:x:11:0:operator:/root:/sbin/nologin
games:x:12:100:games:/usr/games:/sbin/nologin
gopher:x:13:30:gopher:/var/gopher:/sbin/nologin
ftp:x:14:50:FTP User:/var/ftp:/sbin/nologin
nobody:x:99:99:Nobody:/:/sbin/nologin
vcsa:x:69:69:virtual console memory owner:/dev:/sbin/nologin
saslauth:x:499:76:"Saslauthd user":/var/empty/saslauth:/sbin/nologin
postfix:x:89:89::/var/spool/postfix:/sbin/nologin
sshd:x:74:74:Privilege-separated SSH:/var/empty/sshd:/sbin/nologin
raffles:x:2700:501::/home/raffles:/bin/bash
orchard:x:2800:500::/home/orchard:/bin/bash
[root@ip-172-31-9-250 ~]#

[root@ip-172-31-9-250 ~]# cat /etc/group
root:x:0:
bin:x:1:bin,daemon
daemon:x:2:bin,daemon
sys:x:3:bin,adm
adm:x:4:adm,daemon
tty:x:5:
disk:x:6:
lp:x:7:daemon
mem:x:8:
kmem:x:9:
wheel:x:10:
mail:x:12:mail,postfix
uucp:x:14:
man:x:15:
games:x:20:
gopher:x:30:
video:x:39:
dip:x:40:
ftp:x:50:
lock:x:54:
audio:x:63:
nobody:x:99:
users:x:100:
floppy:x:19:
vcsa:x:69:
utmp:x:22:
utempter:x:35:
cdrom:x:11:
tape:x:33:
dialout:x:18:
saslauth:x:76:
postdrop:x:90:
postfix:x:89:
sshd:x:74:
shops:x:500:orchard
walks:x:501:raffles
[root@ip-172-31-9-250 ~]
</code></pre>
