---
date: 2023-07-01
title: Create systemd service for OpenBullet2
categories:
  - guides
  - general
author_staff_member: admin
---

Only for web version

# Steps:
## Create system file: <br>
```bash
cd /usr/lib/systemd/system
nano openbullet2.service
```
## Set your values
Set your path to Openbullet.dll ```ExecStart=dotnet PATH_TO_DLL```<br>
And path to working directory ```WorkingDirectory= PATH_TO_DIR```<br>
Copy paste and save file: <br>
```
[Unit]
Description=OpenBullet2 systemd console application

[Service]
SyslogIdentifier=openbullet2

# systemd will run this executable to start the service
# if /usr/bin/dotnet doesn't work, use `which dotnet` to find correct dotnet executable path
ExecStart=dotnet /root/OpenBullet2/OpenBullet2.dll
WorkingDirectory=/root/OpenBullet2/
# restart
Restart=on-failure
# wait 10sec then restart
RestartSec=10s
#set your username
User=root

# This environment variable is necessary when dotnet isn't loaded for the specified user.
# To figure out this value, run 'env | grep DOTNET_ROOT' when dotnet has been loaded into your shel>
Environment=DOTNET_ROOT=/usr/lib64/dotnet

[Install]
WantedBy=multi-user.target
```

## Run service: 
```bash
systemctl start openbullet2
```
