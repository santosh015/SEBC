```
swappiness :

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "cat /proc/sys/vm/swappiness"
54.254.163.203 | SUCCESS | rc=0 >>
10

54.254.155.190 | SUCCESS | rc=0 >>
10

54.254.159.162 | SUCCESS | rc=0 >>
10

54.169.146.33 | SUCCESS | rc=0 >>
10

54.169.203.196 | SUCCESS | rc=0 >>
10

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$

All my instances have only root volumes, but just in case, noatime and reserved:

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "mount -v"
54.254.155.190 | SUCCESS | rc=0 >>
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

54.169.146.33 | SUCCESS | rc=0 >>
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

54.254.159.162 | SUCCESS | rc=0 >>
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

54.169.203.196 | SUCCESS | rc=0 >>
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

54.254.163.203 | SUCCESS | rc=0 >>
/dev/xvde on / type ext4 (rw)
proc on /proc type proc (rw)
sysfs on /sys type sysfs (rw)
devpts on /dev/pts type devpts (rw,gid=5,mode=620)
tmpfs on /dev/shm type tmpfs (rw,rootcontext="system_u:object_r:tmpfs_t:s0")
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw)

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$

Limits:

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "cat /etc/security/limits.d/cdh.conf"
54.254.155.190 | SUCCESS | rc=0 >>
hdfs       -     nofile   32768   
hdfs       -     nproc    32768   
mapred     -     nofile   32768   
mapred     -     nproc    32768   
hbase      -     nofile   32768   
hbase      -     nproc    32768   

54.169.146.33 | SUCCESS | rc=0 >>
hdfs       -     nofile   32768   
hdfs       -     nproc    32768   
mapred     -     nofile   32768   
mapred     -     nproc    32768   
hbase      -     nofile   32768   
hbase      -     nproc    32768   

54.254.163.203 | SUCCESS | rc=0 >>
hdfs       -     nofile   32768   
hdfs       -     nproc    32768   
mapred     -     nofile   32768   
mapred     -     nproc    32768   
hbase      -     nofile   32768   
hbase      -     nproc    32768   

54.254.159.162 | SUCCESS | rc=0 >>
hdfs       -     nofile   32768   
hdfs       -     nproc    32768   
mapred     -     nofile   32768   
mapred     -     nproc    32768   
hbase      -     nofile   32768   
hbase      -     nproc    32768   

54.169.203.196 | SUCCESS | rc=0 >>
hdfs       -     nofile   32768   
hdfs       -     nproc    32768   
mapred     -     nofile   32768   
mapred     -     nproc    32768   
hbase      -     nofile   32768   
hbase      -     nproc    32768   

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$

Forward and reverse DNS:

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "dig ip-172-31-10-136 +short;dig -x 54.254.163.203 +short;dig ip-172-31-10-137 +short;dig -x 54.169.146.33 +short;dig ip-172-31-10-138 +short; dig -x 54.254.155.190 +short; dig ip-172-31-10-139 +short; dig -x 54.254.159.162 +short; dig ip-172-31-10-140 +short; dig -x 54.169.203.196 +short"
54.254.163.203 | SUCCESS | rc=0 >>
ec2-54-254-163-203.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-146-33.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-155-190.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-159-162.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-203-196.ap-southeast-1.compute.amazonaws.com.

54.169.203.196 | SUCCESS | rc=0 >>
ec2-54-254-163-203.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-146-33.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-155-190.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-159-162.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-203-196.ap-southeast-1.compute.amazonaws.com.

54.254.155.190 | SUCCESS | rc=0 >>
ec2-54-254-163-203.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-146-33.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-155-190.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-159-162.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-203-196.ap-southeast-1.compute.amazonaws.com.

54.169.146.33 | SUCCESS | rc=0 >>
ec2-54-254-163-203.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-146-33.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-155-190.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-159-162.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-203-196.ap-southeast-1.compute.amazonaws.com.

54.254.159.162 | SUCCESS | rc=0 >>
ec2-54-254-163-203.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-146-33.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-155-190.ap-southeast-1.compute.amazonaws.com.
ec2-54-254-159-162.ap-southeast-1.compute.amazonaws.com.
ec2-54-169-203-196.ap-southeast-1.compute.amazonaws.com.

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$

Service ntpd status:

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "/usr/sbin/ntpq -pn"
54.254.155.190 | SUCCESS | rc=0 >>
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+27.124.125.250  17.46.99.204     2 u    3   64  377  136.254  -36.692   6.324
-202.60.94.15    223.252.32.9     2 u   19   64  377  113.603    9.251   3.859
+103.38.120.36   203.35.83.242    2 u    7   64  377   97.442   11.238   5.686
*27.124.125.252  218.100.43.70    2 u    7   64  377  137.218  -37.978   4.922

54.169.203.196 | SUCCESS | rc=0 >>
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+130.102.128.23  128.138.141.172  2 u   12   64  377  250.008  -18.298   8.687
-59.167.170.228  202.6.131.118    2 u    7   64  377  188.582   39.599  11.707
+192.189.54.33   130.95.179.80    2 u    7   64  377  288.966  -38.242  11.510
*27.124.125.251  130.217.226.51   2 u   16   64  377  136.460  -21.783  10.864

54.169.146.33 | SUCCESS | rc=0 >>
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
-27.124.125.250  17.46.99.204     2 u   12   64  377  135.779  -16.166  24.090
+220.237.117.161 202.46.178.18    2 u   18   64  377  167.300   61.508  40.938
*110.22.136.248  .GPS.            1 u   10   64  377  166.001   57.737  39.897
+129.250.35.250  249.224.99.213   2 u   14   64  377   12.298   44.408  27.097

54.254.163.203 | SUCCESS | rc=0 >>
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+130.102.128.23  128.138.141.172  2 u   10   64  377  198.580  -31.893   4.684
-103.76.40.142   203.14.0.250     3 u   10   64  377   96.842  -16.179   5.086
+202.60.94.11    223.252.32.9     2 u   15   64  377  113.783  -13.887   6.514
*27.124.125.252  218.100.43.70    2 u   10   64  377  137.198  -44.532  11.413

54.254.159.162 | SUCCESS | rc=0 >>
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
+27.124.125.250  17.46.99.204     2 u   11   64  377  137.174  -46.458   8.603
*202.60.94.15    223.252.32.9     2 u   15   64  377  110.307  -11.670  12.092
-192.189.54.33   130.95.179.80    2 u   10   64  377  175.942  -11.577  12.237
+129.250.35.251  249.224.99.213   2 u    4   64  377   15.183   -9.434   9.823

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$

Transparent hugepages :

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ ansible all -m shell -a "grep AnonHugePages /proc/meminfo"
54.254.155.190 | SUCCESS | rc=0 >>
AnonHugePages:         0 kB

54.254.159.162 | SUCCESS | rc=0 >>
AnonHugePages:         0 kB

54.169.203.196 | SUCCESS | rc=0 >>
AnonHugePages:         0 kB

54.169.146.33 | SUCCESS | rc=0 >>
AnonHugePages:         0 kB

54.254.163.203 | SUCCESS | rc=0 >>
AnonHugePages:         0 kB

Santoshs-MacBook-Pro:ansible-ec2-start santoshpanda$ 

```
