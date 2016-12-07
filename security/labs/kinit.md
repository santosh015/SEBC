## Add user principal using cm/admin
<pre><code>
kadmin.local -p cm/admin@KSECURITY.COM
addprinc santosh015@KSECURITY.COM
quit
</code></pre>

## Test that Kerberos is enabled
<pre><code>
su - santosh015
hdfs dfs -ls

Caused by: GSSException: No valid credentials provided (Mechanism level: Failed to find any Kerberos tgt)
	at sun.security.jgss.krb5.Krb5InitCredential.getInstance(Krb5InitCredential.java:147)
	at sun.security.jgss.krb5.Krb5MechFactory.getCredentialElement(Krb5MechFactory.java:121)
	at sun.security.jgss.krb5.Krb5MechFactory.getMechanismContext(Krb5MechFactory.java:187)
	at sun.security.jgss.GSSManagerImpl.getMechanismContext(GSSManagerImpl.java:223)
	at sun.security.jgss.GSSContextImpl.initSecContext(GSSContextImpl.java:212)
	at sun.security.jgss.GSSContextImpl.initSecContext(GSSContextImpl.java:179)
	at com.sun.security.sasl.gsskerb.GssKrb5Client.evaluateChallenge(GssKrb5Client.java:193)
	... 41 more
</code></pre>

## kinit santosh015
<pre><code>
[santosh015@ip-172-31-24-59 ~]$ kinit santosh015
Password for santosh015@KSECURITY.COM:
[santosh015@ip-172-31-24-59 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1260
Default principal: santosh015@KSECURITY.COM

Valid starting     Expires            Service principal
12/07/16 10:30:20  12/08/16 10:30:20  krbtgt/KSECURITY.COM@KSECURITY.COM
	renew until 12/14/16 10:30:20
  [santosh015@ip-172-31-24-59 ~]$ hadoop fs -ls
  Found 4 items
  drwxrwxrwx   - santosh015 santosh015          0 2016-12-07 09:30 2015_11_18
  drwxrwxrwx   - santosh015 santosh015          0 2016-12-07 09:30 2015_11_19
  drwxrwxrwx   - santosh015 santosh015          0 2016-12-07 09:30 2015_11_20
  drwxrwxrwx   - santosh015 santosh015          0 2016-12-07 09:30 2015_11_21
  [santosh015@ip-172-31-24-59 ~]$

## Creating a keytab
<pre><code>
kadmin.local -p cm/admin@KSECURITY.COM
xst -norandkey -k santosh015.keytab santosh015@KSECURITY.COM
mv santosh015.keytab /home/santosh015/
chown santosh015 /home/santosh015/santosh015.keytab
chmod 400 /home/santosh015/santosh015.keytab

kinit -kt santosh015.keytab santosh015@KSECURITY.COM
</code></pre>
