```
kadmin.local:  addprinc cm/admin
WARNING: no policy specified for cm/admin@KSECURITY.COM; defaulting to no policy
Enter password for principal "cm/admin@KSECURITY.COM":
Re-enter password for principal "cm/admin@KSECURITY.COM":
Principal "cm/admin@KSECURITY.COM" created.
kadmin.local:  addprinc santosh015
WARNING: no policy specified for santosh015@KSECURITY.COM; defaulting to no policy
Enter password for principal "santosh015@KSECURITY.COM":
Re-enter password for principal "santosh015@KSECURITY.COM":
Principal "santosh015@KSECURITY.COM" created.

## on the other node

[root@ip-172-31-24-59 ~]# kinit santosh015
Password for santosh015@KSECURITY.COM:
[root@ip-172-31-24-59 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: santosh015@KSECURITY.COM

Valid starting     Expires            Service principal
12/07/16 09:47:06  12/08/16 09:47:06  krbtgt/KSECURITY.COM@KSECURITY.COM
	renew until 12/14/16 09:47:06

```
