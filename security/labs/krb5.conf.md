```
[libdefaults]
 default_realm = KSECURITY.COM
 dns_lookup_realm = false
 dns_lookup_kdc = false
 ticket_lifetime = 24h
 renew_lifetime = 7d
 forwardable = true
 default_tgs_enctypes = aes256-cts-hmac-sha1-96 aes128-cts-hmac-sha1-96 arcfour-hmac-md5
 default_tkt_enctypes = aes256-cts-hmac-sha1-96 aes128-cts-hmac-sha1-96 arcfour-hmac-md5
 permitted_enctypes = aes256-cts-hmac-sha1-96 aes128-cts-hmac-sha1-96 arcfour-hmac-md5


[realms]
 KSECURITY.COM = {
  kdc = ip-172-31-24-58.ap-southeast-1.compute.internal
  admin_server = ip-172-31-24-58.ap-southeast-1.compute.internal
 }
```
