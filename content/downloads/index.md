---
title: Downloads
heading: Select version
description: Linux,Windows x64 or Linux arm64
type: downloads

menu:
  main:
    weight: 1
  footer:
    weight: 1

pricing_table:
  - name: Windows GUI x86_64
    color: "#c5c5c5"
    features:
      - text: WPF forms
        highlight: false
      - text: '[Dotnet 6](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-6.0.405-windows-x64-installer), [Microsoft Visual C++ 2015-2020](https://aka.ms/vs/17/release/vc_redist.x64.exe)'
        highlight: false
      - text: 'Run: OpenBullet2.exe'
        highlight: false
    call_to_action:
      link: https://github.com/openbullet/OpenBullet2/releases/latest/download/OpenBullet2.Native.zip
      text: Download

  - name: Windows WEB x86_64
    color: "#8e8e8e"
    features:
      - text: WEB
        highlight: false
      - text: '[Dotnet 6](https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-6.0.405-windows-x64-installer), [Microsoft Visual C++ 2015-2020](https://aka.ms/vs/17/release/vc_redist.x64.exe)'
        highlight: false
      - text: 'Run:  OpenBullet2.exe'
        highlight: false
    call_to_action:
      link: https://github.com/openbullet/OpenBullet2/releases/latest/download/OpenBullet2.zip
      text: Download

  - name: Linux x86_64
    color: "#4a4a4a"
    features:
      - text: WEB
        highlight: false
      - text: '`sudo apt-get install -y aspnetcore-runtime-6.0`'
        highlight: false
      - text: 'Run: `dotnet OpenBullet2.dll`'
        highlight: false
    call_to_action:
      link: https://github.com/openbullet/OpenBullet2/releases/latest/download/OpenBullet2.zip
      text: Download

  - name: Linux arm64
    color: "#000000"
    features:
      - text: WEB
        highlight: false
      - text: '`sudo apt-get install -y aspnetcore-runtime-6.0`'
        highlight: false
      - text: 'Run: `dotnet OpenBullet2.dll`'
        highlight: false
    call_to_action:
      link: https://github.com/openbullet/OpenBullet2/releases/latest/download/OpenBullet2.zip
      text: Download
faq:
  - question: Is it completely free?
    answer: Yes, its open sourse project, fully free to use.
  - question: Where i can see sourse code of this project?
    answer: "App: https://github.com/openbullet/OpenBullet2<br> Website: https://github.com/openbullet2/openbullet2.github.io"
  - question: Why this app not working on my PC?
    answer: 'Install dotnet 6, VcRedist x64 for windows or aspnetcore-runtime-6.0 for linux. Web version working only in browser at url [http://localhost:5000](http://localhost:5000)'
  - question: Questions?
    answer: Contact me for any further questions at <a href="#">ruri@openbullet.dev</a>.

_enabled_editors:
  - visual
  - content
  - source
---
