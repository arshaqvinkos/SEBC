```sh
[logging]
 default = FILE:/var/log/krb5libs.log
 kdc = FILE:/var/log/krb5kdc.log
 admin_server = FILE:/var/log/kadmind.log

[libdefaults]
default_realm = VINKOS.COM
dns_lookup_kdc = false
dns_lookup_realm = false
ticket_lifetime = 86400
renew_lifetime = 604800
forwardable = true
default_tgs_enctypes = rc4-hmac
default_tkt_enctypes = rc4-hmac
permitted_enctypes = rc4-hmac
udp_preference_limit = 1
kdc_timeout = 3000

[realms]
VINKOS.COM = {
kdc = ec2-54-208-253-250.compute-1.amazonaws.com
admin_server = ec2-54-208-253-250.compute-1.amazonaws.com
}

[domain_realm]
```