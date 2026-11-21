# PostgreSQL Server Settings

## Install
- Method1: Follow the [official website](https://www.postgresql.org/download/)
- Method2: Install from the default repository
```
dnf install postgresql<version number>-server
```

## Initialize Database
```
postgresql-setup --initdb
```

## Start Database Server
```
systemctl enable postgresql.service
systemctl start postgresql.service
```

## Create a User
bash
```
sudo -i -u postgres
psql
```
psql
```
CREATE ROLE <user name> WITH SUPERUSER LOGIN;
ALTER USER <user name> WITH PASSWORD '<password>';
CREATE DATABASE <user name>;
```

## Listen Address and Port
Setting File: `/var/lib/pgsql/data/postgresql.conf`
```
listen_addresses = 'localhost,127.0.0.1,192.168.1.1'
port = 5432
```

## Remote Host's IP Address
Setting File: `/var/lib/pgsql/data/pg_hba.conf`
```
host all all 192.168.1.0/24 scram-sha-256
```

## Open Firewall
```
firewall-cmd --zone=public --permanent --add-port 5432/tcp
firewall-cmd --reload
```

## Enable Password Auth (for PHP requests)
Setting File: `/var/lib/pgsql/data/pg_hba.conf`
### Before
```
# TYPE  DATABASE  USER  ADDRESS  METHOD
local   all       all                  peer
host    all       all   127.0.0.1/32   ident
host    all       all   ::1/128        ident
```
### After
```
# TYPE  DATABASE  USER  ADDRESS  METHOD
local   all       all                    scram-sha-256
host    all       all   127.0.0.1/32     scram-sha-256
host    all       all   192.168.1.0/24   scram-sha-256
host    all       all   ::1/128          scram-sha-256
```

