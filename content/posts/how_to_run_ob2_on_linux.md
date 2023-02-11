---
date: 2021-01-24
title: How to run OpenBullet 2 on Linux
categories:
  - guides
  - general
author_staff_member: admin
---

Only web version is working for Linux

# Steps:
Install dotnet 6: <br>
```bash
sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-6.0

```
Download OpenBullet2: <br>
```bash
wget https://github.com/openbullet/OpenBullet2/releases/latest/download/OpenBullet2.zip && \
  mkdir -p OpenBullet2 && \
  unzip OpenBullet2.zip -d OpenBullet2 && \
  cd OpenBullet2
```
Run programm: 
```bash
dotnet OpenBullet2.dll
```
Open your browser and go to url [http://localhost:5000](http://localhost:5000)

# Remote access
## Cloudflared installation
```bash
[.deb]
    wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb dpkg -i cloudflared-linux-amd64.deb
    sudo dpkg -i /tmp/cloudflared-stable-linux-amd64.deb
[.rpm]
    wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-x86_64.rpm
    sudo rpm -ivh ./cloudflared-linux-x86_64.rpm
```
## Cloudflared run
```bash
cloudflared tunnel --url http://localhost:5000 &
```
