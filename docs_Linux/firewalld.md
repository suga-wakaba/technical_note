# Firewall

## `firewall-cmd` Cheat Sheet
### Drop ICMP Echo Request(ping)
```
firewall-cmd --permanent --zone=public --add-rich-rule='rule icmp-type name="echo-request" drop'
```
### Check Table of Ports
```
firewall-cmd --zone=public --list-ports
```
### Add Port
```
firewall-cmd --zone=public --permanent --add-port 80/tcp
```
### Delete Port
```
firewall-cmd --zone=public --permanent --remove-port 80/tcp
```
### Check Table of Services
```
firewall-cmd --zone=public --list-services
```
### Add Service
```
firewall-cmd --zone=public --permanent --add-service=https
```
### Delete Service
```
firewall-cmd --zone=public --permanent --remove-service=https
```
### Reload Table
```
firewall-cmd --reload
```
