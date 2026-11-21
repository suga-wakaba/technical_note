# DNS
> [!NOTE]
> This is the example which maps example.local to 192.168.1.1

## Install
```
dnf install bind
```

## Edit the config file
File: `/etc/named.conf`
### Before
```
options {
    listen-on port 53 { 127.0.0.1; };
    listen-on-v6 port 53 { ::1; };
    allow-query     { localhost; };
}
```

### After
```
options {
    listen-on port 53 { any; };
    listen-on-v6 port 53 { any; };
    allow-query     { any; };
    recursion yes;
    allow-recursion { any; };
    allow-query-cache { any; };
}

zone "example.local" IN {
    type master;
    file "example.local.zone";
};
```

## Create a Zone File
File: /var/named/example.local.zone
```
$TTL 86400
@   IN  SOA ns1.example.local. admin.example.local. (
        2026110901
        3600
        900
        604800
        86400
)

@       IN  NS  ns1.example.local.
ns1     IN  A   192.168.1.2
@       IN  A   192.168.1.2
```

## Check Config and Test
```
named-checkconf
named-checkzone example.local /var/named/example.local.zone
dig @127.0.0.1 example.local
```

## Start named service
```
systemctl enable named.service
systemctl start named.service
```

## Open Firewall
```
firewall-cmd --zone=public --permanent --add-port 53/tcp
firewall-cmd --zone=public --permanent --add-port 53/udp
firewall-cmd --reload
```

---

## Change Primary DNS Server on Clients
```
# Check Connection NAME
nmcli connection show

# Edit Settings
nmcli connection modify "<NAME>" ipv4.dns "<Primary IP> <Secondary IP>"

# Apply Settings
nmcli connection up "<NAME>"

# Check Settings
nmcli device show | grep IP4.DNS
```

