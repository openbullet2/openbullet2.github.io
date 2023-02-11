---
date: 2021-01-23
title: How to download and start OpenBullet 2
categories:
  - guides
  - general
author_staff_member: ruri
---
# Introduction

In this guide I will explain all the steps needed to get OpenBullet 2 up and running on your system.
There are two official clients for OpenBullet 2, choose the one that better suits your needs.

# Web client (cross-platform)
This is a cross-platform web-based client that can be configured to be accessed remotely. It is also mobile-friendly.
![immagine](https://user-images.githubusercontent.com/48930622/151500940-47036c84-ac96-40d9-8758-b32acd4a8921.png)

# Running a precompiled build
If you don’t want to mess with docker and don’t want to compile your own build, you can use the latest automatically compiled build available on github.

First of all visit this [page](https://github.com/openbullet/OpenBullet2/releases/latest) and download the `OpenBullet2.zip` file (do not select the source code option). Once you downloaded it, unzip it to a folder of your choice.

Now it’s time to install the [asp.net core runtime](https://dotnet.microsoft.com/download/dotnet/6.0) You can find instructions on how to install it on your system at the link provided.

<details>
  <summary>Installing recomendations</summary>
  
  For linux i recomend download oficial [dotnet-installer.sh](https://dot.net/v1/dotnet-install.sh) and run 
  ```bash
  ./dotnet-install.sh -c Current
  ```

  If you dont need to compile OpenBullet2 by yourself you get by with a runtime only 
  ```bash
  ./dotnet-install.sh -c Current --runtime aspnetcore
  ```

  For windows you need [dotnet-sdk-x64](https://dotnet.microsoft.com/en-us/download) and [vcredists](https://aka.ms/vs/17/release/vc_redist.x64.exe)
  
</details>

When you’re done, you can test if it got installed properly by opening a command prompt and typing `dotnet --version`, which should output a version number like `6.0` or above.

Navigate to the folder where the file `OpenBullet2.dll` is located (the one you just unzipped) and launch it by using the following command:

```bash
dotnet ./OpenBullet2.dll
```
If you’re on Windows 64 bit, you can double click on `OpenBullet2.exe` instead to achieve the same result (on Windows 32 bit you need to use the terminal command above).

You should now be able to navigate to `http://localhost:5000` on your browser in order to see the OpenBullet 2 setup screen.

# Using docker
<details>
  <summary>Docker</summary>
  
  Install docker from [Get Docker | Docker Documentation](https://docs.docker.com/get-docker/)
  Create a folder (e.g. on windows you can create `C:/OB2/UserData`) where your settings will be stored, and then run

  ```bash
  docker run --name openbullet2 --rm -p 8069:5000 -v C:/OB2/UserData/:/app/UserData/ -it openbullet/openbullet2:latest
  ```

  and finally navigate to `http://localhost:8069` to access your dockerized OB2 instance!

  Let’s break down the docker command:

  `-p 8069:5000` will map your local port 8069 to the container’s port 5000 where OB2 is listening

  `-v C:/OB2/UserData/:/app/UserData/` will map the `C:/OB2/UserData` directory on your system to the `/app/UserData` directory inside the container so that even if you switch container in the future (e.g. to update your OB2 instance) you won’t lose your settings

  `-it` will start an interactive shell that lets you see the output of the OB2 webserver for debugging purposes. You can remove this if you don’t care about it.
</details>

# Compiling your own build

Install git from [Git - Downloads](https://git-scm.com/downloads)
Install the .NET 6 SDK (not runtime) from [Download .NET 6.0 (Linux, macOS, and Windows)](https://dotnet.microsoft.com/download/dotnet/6.0)
Open your favourite terminal (or git bash) and run

```bash
git clone https://github.com/openbullet/OpenBullet2/
```

now cd into the folder where `OpenBullet2.csproj` resides
```bash
cd OpenBullet2/OpenBullet2
```
and compile OB2 using
```bash
dotnet publish --configuration Release
```
you can then navigate to the publish folder and start OB2 with the usual command

```bash
cd bin/Release/net6.0/publish
dotnet ./OpenBullet2.dll
```
# Native client (Windows only)
This is a WPF-based client that is only available for Windows. It is more responsive than the web-based client but lacks its portability, localization and remote access.
![imagine](https://discourse.openbullet.dev/uploads/default/original/2X/0/013a776bcda72176b9f0cbeb4c6cc54a7129cf6b.png)

# Running a precompiled build
First of all visit [this page](https://github.com/openbullet/OpenBullet2/releases/latest) and download the `OpenBullet2.Native.zip` file (do not select the source code option). Once you downloaded it, unzip it to a folder of your choice.

# 64 bit
If you’re on a 64-bit system, simply double click on `OpenBullet2.Native.exe`. If you don’t have .NET 6 it will prompt you to install it.

# 32 bit
If you’re on a 32-bit system, you will need to install .NET 6 manually if you don’t have it. Download and install the [.NET 6 Desktop Runtime](https://dotnet.microsoft.com/download/dotnet/6.0) for Windows 32-bit.

After that, open a terminal, navigate to the folder where the executable is and launch it using the following command
```bash
dotnet ./OpenBullet2.Native.dll
```

# Compiling your own build
Install git from [Git - Downloads](https://git-scm.com/downloads)
Install the .NET 6 SDK (not runtime) [from Download .NET 6.0 (Linux, macOS, and Windows)](https://dotnet.microsoft.com/download/dotnet/6.0)
Open your favourite terminal (or git bash) and run
```bash
git clone https://github.com/openbullet/OpenBullet2/
```
now cd into the folder where `OpenBullet2.Native.csproj` resides
```bash
cd OpenBullet2/OpenBullet2.Native
```
and compile OB2 Native using
```bash
dotnet publish --configuration Release
```
you can then navigate to the publish folder and double-click on `OpenBullet2.Native.exe` to run it.


[source](https://discourse.openbullet.dev/t/how-to-download-and-start-openbullet-2/29): openbullet.dev
