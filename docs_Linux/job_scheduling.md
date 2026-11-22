# Job Scheduling

## Service File
File: `~/.config/systemd/user/<service_name>.service`
### Service File Example
```
[Unit]
Description=<Service Desctiption(space is ok without quotations)>

[Service]
Type=oneshot
ExecStart=<path to shell script>
```

## Timer File
File: `~/.config/systemd/user/<timer name>.timer`
### Timer File Example
```
[Unit]
Description=<Timer Desctiption(space is ok without quotations)>

[Timer]
OnCalendar=06:00:00 # Every day at 6 AM
#OnCalendar=*:*:00 # Every 1 minute
#OnCalendar=00/3:00 # Every 3 hours

[Install]
WantedBy=timers.target
```

## Start Job Scheduling
### Load Service
```
systemctl --user daemon-reload
```
> [!TIP] If change a timer file, execute this command.

## Enable Timer
```
systemctl --user enable --now <timer name>.timer
```

## Test Service
```
systemctl --user start <service name>.service
```

