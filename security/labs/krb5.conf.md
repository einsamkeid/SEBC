### /etc/krb5.conf
```
[logging]
default = FILE:/var/log/krb5libs.log
kdc = FILE:/var/log/krb5kdc.log
admin_server = FILE:/var/log/kadmind.log

[libdefaults]
default_realm = AP-SOUTHEAST-1.COMPUTE.INTERNAL
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 24H
renew_lifetime = 7d
forwardable = true

[realms]
AP-SOUTHEAST-1.COMPUTE.INTERNAL = {
kdc = ip-10-0-0-73.ap-southeast-1.compute.internal
admin_server = ip-10-0-0-73.ap-southeast-1.compute.internal
}

[domain_realm]
 .ap-southeast-1.compute.internal = AP-SOUTHEAST-1.COMPUTE.INTERNAL
 ap-southeast-1.compute.internal = AP-SOUTHEAST-1.COMPUTE.INTERNAL

```