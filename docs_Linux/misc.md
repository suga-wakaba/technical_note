# Misc Note

## Play Videos on Linux Desktop
```
dnf install --nogpgcheck https://mirrors.rpmfusion.org/free/el/rpmfusion-free-release-$(rpm -E %rhel).noarch.rpm
dnf install --nogpgcheck https://mirrors.rpmfusion.org/nonfree/el/rpmfusion-nonfree-release-$(rpm -E %rhel).noarch.rpm
dnf install gstreamer1-plugins-base gstreamer1-plugins-good gstreamer1-plugins-ugly gstreamer1-plugins-bad-free gstreamer1-libav ffmpeg
```

## Manage Units(Services)
- `systemctl` command manages "unit".
- "service" such as Apache and PostgreSQL is a type of "unit".
- In addition, "socket" and "timer" are a type of "unit".
### Examples of Services
- Apache Web Server: httpd.service
- Fire Wall: firewalld.service
- OpenSSH Server: sshd.service

### Management commands
- Start a Service: `systemctl start <Service Name>`
- Stop a Service: `systemctl stop <Service Name>`
- Reload a Service: `systemctl restart <Service Name>`
- Enable automatic startup: `systemctl enable <Service Name>`
- Disable automatic startup: `systemctl disable <Service Name>`
- List Services: `systemctl list-units --type=service`


## Download Packages for Local Install
This command can download packages including its dependent.
```
dnf download --resolve --destdir=. <package name>
```

## Set Hostname
```
nmcli general hostname <hostname>
```

