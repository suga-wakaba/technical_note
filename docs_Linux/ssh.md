# Open SSH Server

## Edit Settings
File: `/etc/ssh/sshd_config`
```
PermitRootLogin no
AllowUsers <User Name>
Port <Port Number>
PasswordAuthentication no
ClientAliveInterval 60
ClientAliveCountMax 3
```

## Check the Config File
```
sshd -t
```

## Add Client's public key
Add client's public key in `~/.ssh/authorized_keys`


# Client Side
## Generate Key Pair
```
ssh-keygen
```

## SSH Login
```
ssh -p <port> -i <private key> <user name>@<host name>
```

## SFTP Login
```
sftp -P <port> -i <private key> <user name>@<host name>
```

